---
title: _set_se_translator
ms.date: 02/21/2018
apiname:
- _set_se_translator
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
apitype: DLLExport
f1_keywords:
- _set_se_translator
- set_se_translator
helpviewer_keywords:
- set_se_translator function
- exception handling, changing
- _set_se_translator function
ms.assetid: 280842bc-d72a-468b-a565-2d3db893ae0f
ms.openlocfilehash: 23eb4e9016666567771832cefed686cb9197b02f
ms.sourcegitcommit: 7f5b29e24e1be9b5985044a030977485fea0b50c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/17/2019
ms.locfileid: "68299708"
---
# <a name="setsetranslator"></a>_set_se_translator

Задайте функцию обратного вызова для каждого потока, чтобы перевести исключения Win32 (структурированные исключения C++ C) в типизированные исключения.

## <a name="syntax"></a>Синтаксис

```cpp
_se_translator_function _set_se_translator(
    _se_translator_function seTransFunction
);
```

### <a name="parameters"></a>Параметры

*сетрансфунктион*<br/>
Указатель на функцию-преобразователь структурированного исключения языка С, создаваемую пользователем.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на предыдущую функцию-преобразователь, зарегистрированную в **_set_se_translator**, чтобы предыдущую функцию можно было восстановить позже. Если Предыдущая функция не задана, возвращаемое значение можно использовать для восстановления поведения по умолчанию. Это значение может быть **nullptr**.

## <a name="remarks"></a>Примечания

Функция **_set_se_translator** предоставляет способ для управления исключениями Win32 (структурированные исключения C) в C++ виде типизированных исключений. Чтобы разрешить обработку C++ каждого исключения C обработчиком **catch** , сначала определите класс-оболочку исключения c, который можно использовать или производные от, для атрибута определенного типа класса на исключение C. Чтобы использовать этот класс, требуется установить пользовательскую функцию преобразования исключений языка C, которая вызывается внутренним механизмом обработки исключением при каждом возникновении исключения языка C. В функции-трансляторе можно вызвать любое типизированное исключение, которое может быть перехвачено соответствующим C++ обработчиком **catch** .

При использовании **_set_se_translator**необходимо использовать [/EHa](../../build/reference/eh-exception-handling-model.md) .

Чтобы указать пользовательскую функцию перевода, вызовите **_set_se_translator** , используя имя функции перевода в качестве аргумента. Функция-переводчик, которую вы пишете, вызывается один раз для каждого вызова функции в стеке, который содержит блоки **try** . Функции-преобразователя по умолчанию не существует.

Функция-преобразователь не должна делать ничего другого, кроме вызова типизированного исключения языка С++. Если она выполняет какие-либо другие действия, помимо вызова исключения (например, запись в файл журнала), программа может вести себя не так, как ожидалось, поскольку число вызовов функции-преобразователя зависит от платформы.

В многопоточной среде функции-преобразователи поддерживаются отдельно для каждого потока. Каждый новый поток требует установки собственной функции-преобразователя. Таким образом, каждый поток владеет собственной обработкой преобразования. **_set_se_translator** относится только к одному потоку; Другая библиотека DLL может установить другую функцию перевода.

Записываемая функция *сетрансфунктион* должна быть скомпилированной в собственном виде функцией (не скомпилированной с параметром/CLR). Он должен принимать целое число без знака и указатель на структуру Win32 **_EXCEPTION_POINTERS** в качестве аргументов. Аргументы — это возвращаемые значения вызовов функций Win32 API **GetExceptionCode** и **жетексцептионинформатион** соответственно.

```cpp
typedef void (__cdecl *_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );
```

Для **_set_se_translator**существуют особенности при динамической компоновке с CRT; Другая библиотека DLL в процессе может вызвать **_set_se_translator** и заменить свой обработчик своим собственным.

При использовании **_set_se_translator** из управляемого кода (код, скомпилированный с параметром/CLR) или смешанного машинного и управляемого кода следует иметь в виду, что переводчик влияет только на исключения, созданные только в машинном коде. Все управляемые исключения, создаваемые в управляемом коде (например, при вызове `System::Exception`), не маршрутизируются через функцию-преобразователь. Исключения, вызванные в управляемом коде с помощью функции Win32 **RaiseException** или вызванной системным исключением, таким как исключение деления на ноль, направляются через транслятор.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_set_se_translator**|\<eh.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

Этот пример создает оболочку для вызовов, чтобы задать структурированный транслятор исключений и восстановить старый из них в классе `Scoped_SE_Translator`RAII. Этот класс позволяет ввести транслятор с определенной областью в виде единого объявления. Деструктор класса восстанавливает исходный транслятор, когда управление покидает область.

```cpp
// crt_settrans.cpp
// compile with: cl /W4 /EHa crt_settrans.cpp
#include <stdio.h>
#include <windows.h>
#include <eh.h>
#include <exception>

class SE_Exception : public std::exception
{
private:
    const unsigned int nSE;
public:
    SE_Exception() noexcept : SE_Exception{ 0 } {}
    SE_Exception( unsigned int n ) noexcept : nSE{ n } {}
    unsigned int getSeNumber() const noexcept { return nSE; }
};

class Scoped_SE_Translator
{
private:
    const _se_translator_function old_SE_translator;
public:
    Scoped_SE_Translator( _se_translator_function new_SE_translator ) noexcept
        : old_SE_translator{ _set_se_translator( new_SE_translator ) } {}
    ~Scoped_SE_Translator() noexcept { _set_se_translator( old_SE_translator ); }
};

void SEFunc()
{
    __try
    {
        printf( "In __try, about to force exception\n" );
        int x = 5;
        int y = 0;
        int *p = &y;
        *p = x / *p;
    }
    __finally
    {
        printf( "In __finally\n" );
    }
}

void trans_func( unsigned int u, EXCEPTION_POINTERS* )
{
    throw SE_Exception( u );
}

int main()
{
    Scoped_SE_Translator scoped_se_translator{ trans_func };
    try
    {
        SEFunc();
    }
    catch( const SE_Exception& e )
    {
        printf( "Caught a __try exception, error %8.8x.\n", e.getSeNumber() );
    }
}
```

```Output
In __try, about to force exception
In __finally
Caught a __try exception, error c0000094.
```

## <a name="example"></a>Пример

Хотя функциональные возможности, предоставляемые **_set_se_translator** , недоступны в управляемом коде, это сопоставление можно использовать в машинном коде, даже если машинный код находится в компиляции с параметром **/CLR** , если машинный код является указано с `#pragma unmanaged`помощью. Если структурированное исключение создается в управляемом коде, который должен быть сопоставлен, то код, создающий и обрабатывающий исключение, должен быть `#pragma unmanaged`помечен. В следующем коде показано возможное использование. Дополнительные сведения см. в разделе [Директивы Pragma и ключевое слово __Pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).

```cpp
// crt_set_se_translator_clr.cpp
// compile with: cl /W4 /clr crt_set_se_translator_clr.cpp
#include <windows.h>
#include <eh.h>
#include <stdio.h>
#include <exception>

int thrower_func( int i ) {
   int y = 0;
   int *p = &y;
   *p = i / *p;
   return 0;
}

class SE_Exception : public std::exception
{
private:
    const unsigned int nSE;
public:
    SE_Exception() noexcept : SE_Exception{ 0 } {}
    SE_Exception( unsigned int n ) noexcept : nSE{ n } {}
    unsigned int getSeNumber() const noexcept { return nSE; }
};

class Scoped_SE_Translator
{
private:
    const _se_translator_function old_SE_translator;
public:
    Scoped_SE_Translator( _se_translator_function new_SE_translator ) noexcept
        : old_SE_translator{ _set_se_translator( new_SE_translator ) } {}
    ~Scoped_SE_Translator() noexcept { _set_se_translator( old_SE_translator ); }
};

#pragma unmanaged
void my_trans_func( unsigned int u, PEXCEPTION_POINTERS )
{
    throw SE_Exception( u );
}

void DoTest()
{
    try
    {
        thrower_func( 10 );
    }
    catch( const SE_Exception& e )
    {
        printf( "Caught SE_Exception, error %8.8x\n", e.getSeNumber() );
    }
    catch(...)
    {
        printf( "Caught unexpected SEH exception.\n" );
    }
}
#pragma managed

int main() {
    Scoped_SE_Translator scoped_se_translator{ my_trans_func };

    DoTest();
}
```

```Output
Caught SE_Exception, error c0000094
```

## <a name="see-also"></a>См. также

[Процедуры обработки исключений](../../c-runtime-library/exception-handling-routines.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[terminate](terminate-crt.md)<br/>
[unexpected](unexpected-crt.md)<br/>
