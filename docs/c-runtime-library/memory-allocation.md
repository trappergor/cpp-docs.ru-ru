---
title: Выделение памяти
ms.date: 11/18/2020
description: Список функций среды выполнения Microsoft C, используемых для выделения, освобождения и повторного выделения памяти.
f1_keywords:
- c.memory
helpviewer_keywords:
- memory allocation, routines
- memory, managing
- memory, allocation
ms.openlocfilehash: 39be48a4ebdf8ee917395d7b743846196200878d
ms.sourcegitcommit: e82e13b80150fcb27a1387018aafb00d99a3827a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2020
ms.locfileid: "94920746"
---
# <a name="memory-allocation"></a>Выделение памяти

Эти подпрограммы выделяют, освобождают и перераспределяют память.

## <a name="memory-allocation-routines"></a>Подпрограммы выделения памяти

|Подпрограмма|Назначение|
|-------------|---------|
|[`_alloca`](../c-runtime-library/reference/alloca.md), [`_malloca`](../c-runtime-library/reference/malloca.md)|Выделение памяти из стека|
|[`calloc`](../c-runtime-library/reference/calloc.md)|Выделение массива и инициализация его элементов значением 0 (ноль)|
|[`_calloc_dbg`](../c-runtime-library/reference/calloc-dbg.md)|Отладочная версия **`calloc`** . Доступно только в отладочных версиях библиотек времени выполнения|
|[`operator delete`, `operator delete[]`](../c-runtime-library/delete-operator-crt.md)|Свободная память, выделенная в куче |
|[`_expand`](../c-runtime-library/reference/expand.md)|Расширение или сжатие блока памяти без его перемещения|
|[`_expand_dbg`](../c-runtime-library/reference/expand-dbg.md)|Отладочная версия **`_expand`** . Доступно только в отладочных версиях библиотек времени выполнения|
|[`free`](../c-runtime-library/reference/free.md)|Свободная память, выделенная в куче|
|[`_free_dbg`](../c-runtime-library/reference/free-dbg.md)|Отладочная версия **`free`** . Доступно только в отладочных версиях библиотек времени выполнения|
|[`_freea`](../c-runtime-library/reference/freea.md)|Свободная память, выделенная в стеке|
|[`_get_heap_handle`](../c-runtime-library/reference/get-heap-handle.md)|Получите Win32 `HANDLE` в куче среды выполнения C (CRT).|
|[`_heapadd`](../c-runtime-library/heapadd.md)|Добавление памяти в кучу|
|[`_heapchk`](../c-runtime-library/reference/heapchk.md)|Проверка согласованности кучи|
|[`_heapmin`](../c-runtime-library/reference/heapmin.md)|Освободить неиспользуемую память в куче|
|[`_heapset`](../c-runtime-library/heapset.md)|Заполнение свободных записей кучи значением|
|[`_heapwalk`](../c-runtime-library/reference/heapwalk.md)|Получение сведений о каждой записи в куче|
|[`malloc`](../c-runtime-library/reference/malloc.md)|Выделение памяти из кучи|
|[`_malloc_dbg`](../c-runtime-library/reference/malloc-dbg.md)|Отладочная версия **`malloc`** ; доступна только в отладочных версиях библиотек времени выполнения|
|[`_msize`](../c-runtime-library/reference/msize.md)|Возврат размера выделенного блока памяти|
|[`_msize_dbg`](../c-runtime-library/reference/msize-dbg.md)|Отладочная версия **`_msize`** ; доступна только в отладочных версиях библиотек времени выполнения|
|[`new`, `new[]`](../c-runtime-library/new-operator-crt.md)|Выделение блока памяти из кучи|
|[`_query_new_handler`](../c-runtime-library/reference/query-new-handler.md)|Возвращает адрес текущей новой подпрограммы обработчика, установленной **`_set_new_handler`**|
|[`_query_new_mode`](../c-runtime-library/reference/query-new-mode.md)|Получить новый режим обработчика, установленный **`_set_new_mode`** для **`malloc`**|
|[`realloc`](../c-runtime-library/reference/realloc.md)|Перераспределение блока на новый размер|
|[`_realloc_dbg`](../c-runtime-library/reference/realloc-dbg.md)|Отладочная версия **`realloc`** ; доступна только в отладочных версиях библиотек времени выполнения|
|[`_set_new_handler`](../c-runtime-library/reference/set-new-handler.md)|Включить механизм обработки ошибок **`new`** , когда оператору не удается выделить память и включить компиляцию стандартных библиотек C++|
|[`_set_new_mode`](../c-runtime-library/reference/set-new-mode.md)|Установка нового режима обработчика для **`malloc`**|

## <a name="see-also"></a>См. также

[Подпрограммы универсальной среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)