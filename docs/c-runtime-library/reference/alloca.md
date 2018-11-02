---
title: _alloca
ms.date: 11/04/2016
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
helpviewer_keywords:
- memory allocation, stack
- alloca function
- _alloca function
ms.assetid: 74488eb1-b71f-4515-88e1-cdd03b6f8225
ms.openlocfilehash: 7c083e791301d3224709a5fc6c711ceaa6397d38
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50668082"
---
# <a name="alloca"></a>_alloca

Выделение памяти в стеке. Эта функция устарела, поскольку доступна более безопасная версия; см. в разделе [_malloca](malloca.md).

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

**_Alloca** рутинных возвращает **void** указатель на выделенное пространство, которое гарантированно будет подходящим образом выровнено для хранения объектов любого типа объекта. Если *размер* равно 0, **_alloca** выделяет элемент нулевой длины и возвращает допустимый указатель на этот элемент.

Если выделить место в памяти невозможно, создается исключение переполнения стека. Исключение переполнения стека не является исключением C++; это структурированное исключение. Вместо использования обработки исключений C++ необходимо использовать [структурированную обработку исключений](../../cpp/structured-exception-handling-c-cpp.md) (SEH).

## <a name="remarks"></a>Примечания

**_alloca** выделяет *размер* байтов из стека программы. Выделенное пространство освобождается автоматически при выходе из вызывающей функции (не при выделении просто выйдет за пределы области). Таким образом, не следует передавать значение указателя, возвращенное **_alloca** как аргумент [бесплатный](free.md).

Существуют ограничения на явный вызов **_alloca** в обработчике исключений (EH). Подпрограммы обработки исключений, выполняющиеся на процессорах класса x86, работают в своем собственном кадре памяти: они выполняют задачи в области памяти, не основанной на текущем положении указателя стека внешней функции. Наиболее распространенные реализации включают выражения структурной обработки исключений (SEH) Windows NT и выражения catch языка C++. Поэтому явный вызов **_alloca** в любом из следующих сценариев приводит к сбою программы во время возврата к вызывающей подпрограмме EH:

- Выражение фильтра исключений SEH Windows NT: `__except ( _alloca() )`

- Windows NT SEH заключительный обработчик исключений: `__finally { _alloca() }`

- Выражение catch обработки исключений языка C++

Тем не менее **_alloca** могут вызываться непосредственно из подпрограммы обработки исключений или из предоставленную приложением функцию обратного вызова, вызывается одним из ПЕРЕЧИСЛЕННЫХ выше сценариев.

> [!IMPORTANT]
> В Windows XP Если **_alloca** вызывается внутри блока try/catch, необходимо вызвать метод [_resetstkoflw](resetstkoflw.md) в блоке catch.

Помимо вышеуказанных ограничений при использовании[/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) параметр, **_alloca** не может использоваться в **__except** блоков. Для получения дополнительной информации см. [/clr Restrictions](../../build/reference/clr-restrictions.md).

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
