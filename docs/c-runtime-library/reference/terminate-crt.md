---
title: terminate (CRT)
ms.date: 11/04/2016
api_name:
- terminate
api_location:
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
- api-ms-win-crt-runtime-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- terminate
helpviewer_keywords:
- terminate function
- exception handling, termination
ms.assetid: 90e67402-08e9-4b2a-962c-66a8afd3ccb4
ms.openlocfilehash: b76ce42817fa1a6b79ef32965fcfa550a508e88d
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70946197"
---
# <a name="terminate-crt"></a>terminate (CRT)

Вызывает [Abort](abort.md) или функцию, указанную с помощью **set_terminate**.

## <a name="syntax"></a>Синтаксис

```C
void terminate( void );
```

## <a name="remarks"></a>Примечания

Функция **Terminate** используется с C++ обработкой исключений и вызывается в следующих случаях:

- не удается найти подходящий обработчик catch для исключения C++;

- исключение создано деструктором во время очистки стека;

- стек поврежден после возникновения исключения.

по умолчанию [прерывания вызовов прерывается](abort.md) . Это значение по умолчанию можно изменить, создав собственную функцию завершения и вызвав **set_terminate** с именем функции в качестве аргумента. Функция **Terminate** вызывает последнюю функцию, заданную в качестве аргумента для **set_terminate**. Дополнительные сведения см. в разделе [Необработанные исключения C++](../../cpp/unhandled-cpp-exceptions.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**terminate**|\<eh.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="example"></a>Пример

```cpp
// crt_terminate.cpp
// compile with: /EHsc
#include <eh.h>
#include <process.h>
#include <iostream>
using namespace std;

void term_func();

int main()
{
    int i = 10, j = 0, result;
    set_terminate( term_func );
    try
    {
        if( j == 0 )
            throw "Divide by zero!";
        else
            result = i/j;
    }
    catch( int )
    {
        cout << "Caught some integer exception.\n";
    }
    cout << "This should never print.\n";
}

void term_func()
{
    cout << "term_func() was called by terminate().\n";

    // ... cleanup tasks performed here

    // If this function does not exit, abort is called.

    exit(-1);
}
```

```Output
term_func() was called by terminate().
```

## <a name="see-also"></a>См. также

[Процедуры обработки исключений](../../c-runtime-library/exception-handling-routines.md)<br/>
[abort](abort.md)<br/>
[_set_se_translator](set-se-translator.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[unexpected](unexpected-crt.md)<br/>
