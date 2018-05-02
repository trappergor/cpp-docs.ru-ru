---
title: _alloca | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: ''
ms.topic: reference
apiname:
- _alloca
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
- _alloca
- alloca
dev_langs:
- C++
helpviewer_keywords:
- memory allocation, stack
- alloca function
- _alloca function
ms.assetid: 74488eb1-b71f-4515-88e1-cdd03b6f8225
caps.latest.revision: 23
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 27ee6e3c63a086ad2371350baddd038a93f36794
ms.sourcegitcommit: ef859ddf5afea903711e36bfd89a72389a12a8d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2018
---
# <a name="alloca"></a>_alloca

Выделение памяти в стеке. Эта функция рекомендуется, поскольку существует более безопасная версия доступна; в разделе [_malloca](malloca.md).

## <a name="syntax"></a>Синтаксис

```C
void *_alloca(
   size_t size
);
```

### <a name="parameters"></a>Параметры

*size*<br/>
Байты, которые нужно выделить из стека.

## <a name="return-value"></a>Возвращаемое значение

**_Alloca** сопоставление возвращает **void** указатель на выделенное пространство, которое гарантированно будет соответственно выровнено для хранения объектов любого типа объекта. Если *размер* равно 0, **_alloca** выделяет элемент нулевой длины и возвращает допустимый указатель к элементу.

Если выделить место в памяти невозможно, создается исключение переполнения стека. Исключение переполнения стека не является исключением C++; это структурированное исключение. Вместо использования обработки исключений C++ необходимо использовать [структурированную обработку исключений](../../cpp/structured-exception-handling-c-cpp.md) (SEH).

## <a name="remarks"></a>Примечания

**_alloca** выделяет *размер* байтов из стека программы. Выделенное пространство освобождается автоматически при выходе из вызывающей функции, (не при распределении просто выйдет за пределы области). Таким образом, не передавайте значение указателя, возвращенное **_alloca** как аргумент [свободного](free.md).

Существуют ограничения на явный вызов **_alloca** в обработчике исключений (EH). Подпрограммы обработки исключений, выполняющиеся на процессорах класса x86, работают в своем собственном кадре памяти: они выполняют задачи в области памяти, не основанной на текущем положении указателя стека внешней функции. Наиболее распространенные реализации включают выражения структурной обработки исключений (SEH) Windows NT и выражения catch языка C++. Поэтому явный вызов **_alloca** в любом из следующих сценариев приводит к сбою программы во время возврата к вызывающей подпрограмме EH:

- Windows NT выражение фильтрации исключений: `__except ( _alloca() )`

- Windows NT SEH заключительный обработчик исключений: `__finally { _alloca() }`

- Выражение catch обработки исключений языка C++

Тем не менее **_alloca** может вызываться непосредственно из подпрограммы обработки исключений или предоставленного приложением обратного вызова, который вызывается одним из перечисленных выше сценариев обработки исключений.

> [!IMPORTANT]
> В Windows XP Если **_alloca** вызывается внутри блока try/catch, необходимо вызвать метод [_resetstkoflw](resetstkoflw.md) в блоке catch.

Помимо вышеуказанным ограничений при использовании[/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) параметр **_alloca** не может использоваться в **__except** блоков. Для получения дополнительной информации см. [/clr Restrictions](../../build/reference/clr-restrictions.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_alloca**|\<malloc.h>|

## <a name="example"></a>Пример

```C
// crt_alloca.c
// This program demonstrates the use of
// _alloca and trapping any exceptions
// that may occur.

#include <windows.h>
#include <stdio.h>
#include <malloc.h>

int main()
{
    int     size = 1000;
    int     errcode = 0;
    void    *pData = NULL;

    // Note: Do not use try/catch for _alloca,
    // use __try/__except, since _alloca throws
    // Structured Exceptions, not C++ exceptions.

    __try {
        // An unbounded _alloca can easily result in a
        // stack overflow.
        // Checking for a size < 1024 bytes is recommended.
        if (size > 0 && size < 1024)
        {
            pData = _alloca( size );
            printf_s( "Allocated %d bytes of stack at 0x%p",
                      size, pData);
        }
        else
        {
            printf_s("Tried to allocate too many bytes.\n");
        }
    }

    // If an exception occured with the _alloca function
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )
    {
        printf_s("_alloca failed!\n");

        // If the stack overflows, use this function to restore.
        errcode = _resetstkoflw();
        if (errcode)
        {
            printf_s("Could not reset the stack!\n");
            _exit(1);
        }
    };
}
```

```Output
Allocated 1000 bytes of stack at 0x0012FB50
```

## <a name="see-also"></a>См. также

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_resetstkoflw](resetstkoflw.md)<br/>
[_malloca](malloca.md)<br/>
