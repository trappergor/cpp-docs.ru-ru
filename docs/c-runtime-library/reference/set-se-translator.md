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
ms.openlocfilehash: 18ee500d7b884d1934c29dc91d9bcb03d507680d
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57808382"
---
# <a name="setsetranslator"></a>_set_se_translator

Задайте функцию обратного вызова отдельного потока для преобразования исключения Win32 (структурированные исключения C) в C++ типизированные исключения.

## <a name="syntax"></a>Синтаксис

```cpp
_se_translator_function _set_se_translator(
    _se_translator_function seTransFunction
);
```

### <a name="parameters"></a>Параметры

*seTransFunction*<br/>
Указатель на функцию-преобразователь структурированного исключения языка С, создаваемую пользователем.

## <a name="return-value"></a>Возвращаемое значение

Возвращает указатель на предыдущую функцию-преобразователь, зарегистрированную с помощью **_set_se_translator**так, чтобы можно было впоследствии восстановить предыдущую функцию. Если предыдущая функция не задана, возвращаемое значение может использоваться для восстановления поведения по умолчанию; Это значение может быть **nullptr**.

## <a name="remarks"></a>Примечания

**_Set_se_translator** функция предоставляет способ обработки исключений Win32 (структурированные исключения C) как C++ типизированные исключения. Чтобы разрешить каждое исключение языка с ++ обрабатывать **catch** обработчик, сначала определить класс-оболочку исключения C, который можно использовать, или производным от, для атрибута специального типа класса исключению языка c. Чтобы использовать этот класс, требуется установить пользовательскую функцию преобразования исключений языка C, которая вызывается внутренним механизмом обработки исключением при каждом возникновении исключения языка C. Внутри функции-преобразователя, можно вызывать любое типизированное исключение, которое может перехватываться соответствующим C++ **catch** обработчика.

Необходимо использовать [/EHa](../../build/reference/eh-exception-handling-model.md) при использовании **_set_se_translator**.

Чтобы указать пользовательскую функцию преобразования, вызовите **_set_se_translator** с помощью имя функции преобразования в качестве аргумента. Функция-преобразователь вызывается один раз для каждого вызова функции в стеке, который имеет **попробуйте** блоков. Функции-преобразователя по умолчанию не существует.

Функция-преобразователь не должна делать ничего другого, кроме вызова типизированного исключения языка С++. Если она выполняет какие-либо другие действия, помимо вызова исключения (например, запись в файл журнала), программа может вести себя не так, как ожидалось, поскольку число вызовов функции-преобразователя зависит от платформы.

В многопоточной среде функции-преобразователи поддерживаются отдельно для каждого потока. Каждый новый поток требует установки собственной функции-преобразователя. Таким образом, каждый поток владеет собственной обработкой преобразования. **_set_se_translator** относится только к одному потоку; другая DLL может установить другую функцию преобразования.

*SeTransFunction* созданная функция должна быть функцией скомпилированного как собственный (не компилируется с параметром/CLR). Она должна выполнить целое число без знака и указатель в Win32 **_EXCEPTION_POINTERS** структуры в качестве аргументов. Аргументы являются возвращаемыми значениями вызовов Win32 API **GetExceptionCode** и **GetExceptionInformation** функции, соответственно.

```cpp
typedef void (__cdecl *_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );
```

Для **_set_se_translator**, существуют последствия, динамическое связывание с CRT; другой библиотеки DLL в процессе может вызвать **_set_se_translator** и заменить обработчик собственным.

При использовании **_set_se_translator** из управляемого кода (кода, скомпилированного с параметром/CLR) или смешанного машинного и управляемого кода, имейте в виду, что преобразователь влияет на исключения, создаваемые в отлаживать только машинный код. Все управляемые исключения, создаваемые в управляемом коде (например, при вызове `System::Exception`), не маршрутизируются через функцию-преобразователь. Исключения, вызванные в управляемом коде, с помощью функции Win32 **RaiseException** или вызванные системным исключением как исключение деления на ноль, маршрутизируются через преобразователь.

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_set_se_translator**|\<eh.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

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
    unsigned int nSE;
public:
    SE_Exception() : nSE{ 0 } {}
    SE_Exception( unsigned int n ) : nSE{ n } {}
    unsigned int getSeNumber() { return nSE; }
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

void trans_func(unsigned int u, EXCEPTION_POINTERS*)
{
    throw SE_Exception(u);
}

int main()
{
    auto original = _set_se_translator(trans_func);
    try
    {
        SEFunc();
    }
    catch(SE_Exception& e)
    {
        printf("Caught a __try exception, error %8.8x.\n", e.getSeNumber());
    }
    _set_se_translator(original);
}
```

```Output
In __try, about to force exception
In __finally
Caught a __try exception, error c0000094.
```

## <a name="example"></a>Пример

Несмотря на то, что функциональные возможности, предоставляемые **_set_se_translator** — нет доступа в управляемом коде, можно использовать это сопоставление в машинном коде, даже если этот машинный код скомпилирован с **/CLR** переключиться, до тех пор, пока машинный код помечен директивой `#pragma unmanaged`. Если структурированное исключение создается в управляемом коде, должны быть сопоставлены, код, который создает исключение и обрабатывающий его должен быть помечен `#pragma unmanaged`. В следующем коде показано возможное использование. Дополнительные сведения см. в разделе [Директивы Pragma и ключевое слово __Pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).

```cpp
// crt_set_se_translator_clr.cpp
// compile with: cl /W4 /clr crt_set_se_translator_clr.cpp
#include <windows.h>
#include <eh.h>
#include <assert.h>
#include <stdio.h>
#include <exception>

int thrower_func(int i) {
   int y = 0;
   int *p = &y;
   *p = i / *p;
   return 0;
}

class SE_Exception : public std::exception {
private:
    unsigned int nSE;
public:
    SE_Exception() : nSE{ 0 } {}
    SE_Exception(unsigned int n) : nSE{ n } {}
    unsigned int getSeNumber() { return nSE; }
};

#pragma unmanaged
void my_trans_func(unsigned int u, PEXCEPTION_POINTERS)
{
    throw SE_Exception(u);
}

void DoTest()
{
    try
    {
        thrower_func(10);
    }
    catch(SE_Exception& e)
    {
        printf("Caught SE_Exception, error %8.8x\n", e.getSeNumber());
    }
    catch(...)
    {
        printf("Caught unexpected SEH exception.\n");
    }
}
#pragma managed

int main() {
    auto original = _set_se_translator(my_trans_func);
    DoTest();
    _set_se_translator(original);
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
