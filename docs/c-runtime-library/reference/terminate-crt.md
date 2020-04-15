---
title: terminate (CRT)
ms.date: 4/2/2020
api_name:
- terminate
- _o_terminate
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
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 1aa95daeab424c933f10060fb4f87cb317aa188c
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362547"
---
# <a name="terminate-crt"></a>terminate (CRT)

Вызовы [прерываются](abort.md) или функция, указанная с помощью **set_terminate.**

## <a name="syntax"></a>Синтаксис

```C
void terminate( void );
```

## <a name="remarks"></a>Remarks

Функция **завершения** используется при обработке исключений с СЗ и вызывается в следующих случаях:

- не удается найти подходящий обработчик catch для исключения C++;

- исключение создано деструктором во время очистки стека;

- стек поврежден после возникновения исключения.

**прекратить** [выполнение](abort.md) вызовов по умолчанию. Вы можете изменить этот дефолт, написав собственную функцию прекращения и вызывая **set_terminate** с именем вашей функции в качестве аргумента. **прекратить** вызовы последней функции, данной в качестве аргумента для **set_terminate.** Дополнительные сведения см. в разделе [Необработанные исключения C++](../../cpp/unhandled-cpp-exceptions.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**Прекратить**|\<eh.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Процедуры обработки исключений](../../c-runtime-library/exception-handling-routines.md)<br/>
[Прервать](abort.md)<br/>
[_set_se_translator](set-se-translator.md)<br/>
[set_terminate](set-terminate-crt.md)<br/>
[set_unexpected](set-unexpected-crt.md)<br/>
[Неожиданные](unexpected-crt.md)<br/>
