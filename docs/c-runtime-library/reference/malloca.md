---
title: _malloca
ms.date: 11/04/2016
apiname:
- _malloca
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
- malloca
- _malloca
helpviewer_keywords:
- memory allocation, stack
- malloca function
- _malloca function
ms.assetid: 293992df-cfca-4bc9-b313-0a733a6bb936
ms.openlocfilehash: 8c8ce8bdf8ab40cae45ecec9c4b182bdf3d6bc82
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50563986"
---
# <a name="malloca"></a>_malloca

Выделение памяти в стеке. Это версия функции [_alloca](alloca.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).

## <a name="syntax"></a>Синтаксис

```C
void *_malloca(
   size_t size
);
```

### <a name="parameters"></a>Параметры

*size*<br/>
Байты, которые нужно выделить из стека.

## <a name="return-value"></a>Возвращаемое значение

**_Malloca** рутинных возвращает **void** указатель на выделенное пространство, которое гарантированно будет подходящим образом выровнено для хранения объектов любого типа объекта. Если *размер* равно 0, **_malloca** выделяет элемент нулевой длины и возвращает допустимый указатель на этот элемент.

Если выделить место в памяти невозможно, создается исключение переполнения стека. Исключение переполнения стека не является исключением C++; это структурированное исключение. Вместо использования обработки исключений C++ необходимо использовать [структурированную обработку исключений](../../cpp/structured-exception-handling-c-cpp.md) (SEH).

## <a name="remarks"></a>Примечания

**_malloca** выделяет *размер* байтов из стека программы или кучи, если запрос превышает определенный размер в байтах, определяемый **_ALLOCA_S_THRESHOLD**. Разница между **_malloca** и **_alloca** является то, что **_alloca** всегда выделяет память из стека, независимо от размера. В отличие от **_alloca**, который не требует и не позволяет вызывать **бесплатный** для освобождения памяти, выделенной таким образом, **_malloca** требует использования [_freea](freea.md)для освобождения памяти. В режиме отладки **_malloca** всегда выделяет память из кучи.

Существуют ограничения на явный вызов **_malloca** в обработчике исключений (EH). Подпрограммы обработки исключений, выполняющиеся на процессорах класса x86, работают в своем собственном кадре памяти: они выполняют задачи в области памяти, не основанной на текущем положении указателя стека внешней функции. Наиболее распространенные реализации включают выражения структурной обработки исключений (SEH) Windows NT и выражения catch языка C++. Поэтому явный вызов **_malloca** в любом из следующих сценариев приводит к сбою программы во время возврата к вызывающей подпрограмме EH:

- Выражение фильтра исключений SEH Windows NT: **__except** (`_malloca ()` )

- Windows NT SEH заключительный обработчик исключений: **__finally** {`_malloca ()` }

- Выражение catch обработки исключений языка C++

Тем не менее **_malloca** могут вызываться непосредственно из подпрограммы обработки исключений или из предоставленную приложением функцию обратного вызова, вызывается одним из ПЕРЕЧИСЛЕННЫХ выше сценариев.

> [!IMPORTANT]
> В Windows XP Если **_malloca** вызывается внутри блока try/catch, необходимо вызвать метод [_resetstkoflw](resetstkoflw.md) в блоке catch.

Помимо вышеуказанных ограничений при использовании [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) параметр, **_malloca** не может использоваться в **__except** блоков. Для получения дополнительной информации см. [/clr Restrictions](../../build/reference/clr-restrictions.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_malloca**|\<malloc.h>|

## <a name="example"></a>Пример

```C
// crt_malloca_simple.c
#include <stdio.h>
#include <malloc.h>

void Fn()
{
   char * buf = (char *)_malloca( 100 );
   // do something with buf
   _freea( buf );
}

int main()
{
   Fn();
}
```

## <a name="example"></a>Пример

```C
// crt_malloca_exception.c
// This program demonstrates the use of
// _malloca and trapping any exceptions
// that may occur.

#include <windows.h>
#include <stdio.h>
#include <malloc.h>

int main()
{
    int     size;
    int     numberRead = 0;
    int     errcode = 0;
    void    *p = NULL;
    void    *pMarker = NULL;

    while (numberRead == 0)
    {
        printf_s("Enter the number of bytes to allocate "
                 "using _malloca: ");
        numberRead = scanf_s("%d", &size);
    }

    // Do not use try/catch for _malloca,
    // use __try/__except, since _malloca throws
    // Structured Exceptions, not C++ exceptions.

    __try
    {
        if (size > 0)
        {
            p =  _malloca( size );
        }
        else
        {
            printf_s("Size must be a positive number.");
        }
        _freea( p );
    }

    // Catch any exceptions that may occur.
    __except( GetExceptionCode() == STATUS_STACK_OVERFLOW )
    {
        printf_s("_malloca failed!\n");

        // If the stack overflows, use this function to restore.
        errcode = _resetstkoflw();
        if (errcode)
        {
            printf("Could not reset the stack!");
            _exit(1);
        }
    };
}
```

### <a name="input"></a>Входные данные

```Input
1000
```

### <a name="sample-output"></a>Пример результатов выполнения

```Output
Enter the number of bytes to allocate using _malloca: 1000
```

## <a name="see-also"></a>См. также

[Выделение памяти](../../c-runtime-library/memory-allocation.md)<br/>
[calloc](calloc.md)<br/>
[malloc](malloc.md)<br/>
[realloc](realloc.md)<br/>
[_resetstkoflw](resetstkoflw.md)<br/>
