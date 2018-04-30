---
title: _set_se_translator | Документы Майкрософт
ms.custom: ''
ms.date: 02/21/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
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
dev_langs:
- C++
helpviewer_keywords:
- set_se_translator function
- exception handling, changing
- _set_se_translator function
ms.assetid: 280842bc-d72a-468b-a565-2d3db893ae0f
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: cec991656546b4985dc34938382c406cea596253
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="setsetranslator"></a>_set_se_translator

Задайте функцию обратного вызова отдельного потока для перевода исключения Win32 (структурированные исключения C) в C++ типизированные исключения.

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

Возвращает указатель на предыдущую функцию-преобразователь, зарегистрированные с **_set_se_translator**таким образом, чтобы можно было впоследствии восстановить предыдущую функцию. Если предыдущая функция не задана, возвращаемое значение может использоваться для восстановления поведения по умолчанию; Это значение может быть **nullptr**.

## <a name="remarks"></a>Примечания

**_Set_se_translator** функция предоставляет способ обработки исключений Win32 (структурированные исключения C) как C++ типизированные исключения. Чтобы разрешить для с ++ обрабатывать каждое исключение языка C **перехватывать** обработчик, сначала определите класс-оболочку исключения C, который можно использовать или производными, атрибута специального типа класса исключению языка c. Чтобы использовать этот класс, требуется установить пользовательскую функцию преобразования исключений языка C, которая вызывается внутренним механизмом обработки исключением при каждом возникновении исключения языка C. В функции-преобразователя можно вызывать любое типизированное исключение, которое может быть перехвачено сопоставления C++ **перехватывать** обработчика.

Необходимо использовать [/EHa](../../build/reference/eh-exception-handling-model.md) при использовании **_set_se_translator**.

Чтобы указать пользовательскую функцию преобразования, вызовите **_set_se_translator** имени функции преобразования в качестве аргумента. Функция-преобразователь, который написать вызывается один раз для каждого вызова функции для стека, имеющего **повторите** блоков. Функции-преобразователя по умолчанию не существует.

Функция-преобразователь не должна делать ничего другого, кроме вызова типизированного исключения языка С++. Если она выполняет какие-либо другие действия, помимо вызова исключения (например, запись в файл журнала), программа может вести себя не так, как ожидалось, поскольку число вызовов функции-преобразователя зависит от платформы.

В многопоточной среде функции-преобразователи поддерживаются отдельно для каждого потока. Каждый новый поток требует установки собственной функции-преобразователя. Таким образом, каждый поток владеет собственной обработкой преобразования. **_set_se_translator** относится только к одному потоку; другая DLL может установить другую функцию преобразования.

*SeTransFunction* функция должна быть функцией компилируется в машинный код (не компилируется с параметром/CLR). Она должна принимать целое число без знака и указатель на объект Win32 **_EXCEPTION_POINTERS** структуры в качестве аргументов. Аргументы являются возвращаемыми значениями вызовов Win32 API **GetExceptionCode** и **GetExceptionInformation** функции, соответственно.

```cpp
typedef void (__cdecl *_se_translator_function)(unsigned int, struct _EXCEPTION_POINTERS* );
```

Для **_set_se_translator**, существуют проблемы, когда динамическая компоновка с библиотекой CRT; другой DLL в процессе может вызвать **_set_se_translator** и заменить обработчик собственным.

При использовании **_set_se_translator** из управляемого кода (кода, скомпилированного с параметром/CLR) или смеси машинного и управляемого кода, имейте в виду, что преобразователь влияет только на исключения, создаваемые в машинном коде. Все управляемые исключения, создаваемые в управляемом коде (например, при вызове `System::Exception`), не маршрутизируются через функцию-преобразователь. Исключения, вызванные в управляемом коде с помощью функции Win32 **RaiseException** или вызванные системным исключением, таким как исключение деления на ноль, маршрутизируются через преобразователь.

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

class SE_Exception
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

Несмотря на то, что функциональные возможности, предоставляемые **_set_se_translator** — недоступны в управляемом коде, можно использовать это сопоставление в машинном коде, даже когда этот машинный код скомпилирован с **/CLR** Переключение, при условии, что машинный код помечен директивой `#pragma unmanaged`. Если структурированное исключение создается в управляемом коде, который должен быть сопоставлен, код, который создает и обрабатывает исключение, должен быть помечен `#pragma unmanaged`. В следующем коде показано возможное использование. Дополнительные сведения см. в разделе [Директивы Pragma и ключевое слово __Pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md).

```cpp
// crt_set_se_translator_clr.cpp
// compile with: cl /W4 /clr crt_set_se_translator_clr.cpp
#include <windows.h>
#include <eh.h>
#include <assert.h>
#include <stdio.h>

int thrower_func(int i) {
   int y = 0;
   int *p = &y;
   *p = i / *p;
   return 0;
}

class CMyException{
private:
    unsigned int nSE;
public:
    CMyException() : nSE{ 0 } {}
    CMyException(unsigned int n) : nSE{ n } {}
    unsigned int getSeNumber() { return nSE; }
};

#pragma unmanaged
void my_trans_func(unsigned int u, PEXCEPTION_POINTERS)
{
    throw CMyException(u);
}

void DoTest()
{
    try
    {
        thrower_func(10);
    }
    catch(CMyException e)
    {
        printf("Caught CMyException.\n");
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
Caught CMyException, error c0000094
```

## <a name="see-also"></a>См. также

[Процедуры обработки исключений](../../c-runtime-library/exception-handling-routines.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[terminate](terminate-crt.md)<br/>
[unexpected](unexpected-crt.md)<br/>
