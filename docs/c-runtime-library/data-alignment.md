---
title: Выравнивание данных
ms.date: 11/04/2016
f1_keywords:
- data.alignment
helpviewer_keywords:
- data alignment [C++]
ms.assetid: 35ac3d2d-a4b3-421b-954f-b7372b1f18e1
ms.openlocfilehash: 92b8df81751e01e655e348d5f090705e5194312b
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57738803"
---
# <a name="data-alignment"></a>Выравнивание данных

Следующие функции времени выполнения C поддерживают выравнивание данных.

## <a name="data-alignment-routines"></a>Подпрограммы выравнивания данных

|Подпрограмма|Использовать|
|-------------|---------|
|[_aligned_free](../c-runtime-library/reference/aligned-free.md)|Освобождает блок памяти, который был выделен с помощью функции [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) или [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md).|
|[_aligned_free_dbg](../c-runtime-library/reference/aligned-free-dbg.md)|Освобождает блок памяти, который был выделен с помощью [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) или [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) (только отладочная версия).|
|[_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md)|Размещение памяти на указанной границе выравнивания.|
|[_aligned_malloc_dbg](../c-runtime-library/reference/aligned-malloc-dbg.md)|Выделяет память в указанных границах выравнивания с дополнительным пространством для заголовка отладки и буферов перезаписи (только отладочная версия).|
|[_aligned_msize](../c-runtime-library/reference/aligned-msize.md)|Возвращает размер блока памяти, выделенного в куче.|
|[_aligned_msize_dbg](../c-runtime-library/reference/aligned-msize-dbg.md)|Возвращает размер блока памяти, выделенного в куче (только в отладочной версии).|
|[_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md)|Размещение памяти на указанной границе выравнивания.|
|[_aligned_offset_malloc_dbg](../c-runtime-library/reference/aligned-offset-malloc-dbg.md)|Размещение памяти на указанной границе выравнивания (только в отладочной версии).|
|[_aligned_offset_realloc](../c-runtime-library/reference/aligned-offset-realloc.md)|Изменяет размер блока памяти, который был выделен с помощью функции [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) или [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md).|
|[_aligned_offset_realloc_dbg](../c-runtime-library/reference/aligned-offset-realloc-dbg.md)|Изменяет размер блока памяти, который был выделен с помощью функции [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) или [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) (только отладочная версия).|
|[_aligned_offset_recalloc](../c-runtime-library/reference/aligned-offset-recalloc.md)|Изменяет размер блока памяти, который был выделен с помощью [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) или [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md), и инициализирует память нулями.|
|[_aligned_offset_recalloc_dbg](../c-runtime-library/reference/aligned-offset-recalloc-dbg.md)|Изменяет размер блока памяти, который был выделен с помощью [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) или [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md), и инициализирует память нулями (только отладочная версия).|
|[_aligned_realloc](../c-runtime-library/reference/aligned-realloc.md)|Изменяет размер блока памяти, который был выделен с помощью функции [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) или [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md).|
|[_aligned_realloc_dbg](../c-runtime-library/reference/aligned-realloc-dbg.md)|Изменяет размер блока памяти, который был выделен с помощью функции [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) или [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md) (только отладочная версия).|
|[_aligned_recalloc](../c-runtime-library/reference/aligned-recalloc.md)|Изменяет размер блока памяти, который был выделен с помощью [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) или [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md), и инициализирует память нулями.|
|[_aligned_recalloc_dbg](../c-runtime-library/reference/aligned-recalloc-dbg.md)|Изменяет размер блока памяти, который был выделен с помощью [_aligned_malloc](../c-runtime-library/reference/aligned-malloc.md) или [_aligned_offset_malloc](../c-runtime-library/reference/aligned-offset-malloc.md), и инициализирует память нулями (только отладочная версия).|

## <a name="see-also"></a>См. также

[Универсальные подпрограммы среды выполнения C по категориям](../c-runtime-library/run-time-routines-by-category.md)<br/>
