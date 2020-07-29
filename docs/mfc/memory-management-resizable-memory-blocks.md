---
title: Управление памятью. Изменяемые блоки памяти
ms.date: 11/04/2016
helpviewer_keywords:
- memory blocks [MFC], resizable
- memory [MFC], corruption
- memory allocation [MFC], memory block size
- memory blocks [MFC], allocating
- blocks [MFC], memory allocation
- resizable memory blocks [MFC]
ms.assetid: f0efe6f4-a3ed-4541-9195-51ec1291967a
ms.openlocfilehash: 308b5aa00aeb1f0e7887ad90bad79a28b361d7c7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87217926"
---
# <a name="memory-management-resizable-memory-blocks"></a>Управление памятью. Изменяемые блоки памяти

**`new`** Операторы и **`delete`** , описанные в статье [Управление памятью: примеры](memory-management-examples.md), хорошо подходят для выделения и освобождения блоков памяти и объектов фиксированного размера. Иногда приложению может потребоваться изменение размеров блоков памяти. Для управления блоками памяти с изменяемыми размерами в куче необходимо использовать стандартные функции библиотеки времени выполнения C: [malloc](../c-runtime-library/reference/malloc.md), [realloc](../c-runtime-library/reference/realloc.md)и [Free](../c-runtime-library/reference/free.md) .

> [!IMPORTANT]
> Смешивание **`new`** операторов и **`delete`** с изменяемыми функциями выделения памяти в одном блоке памяти приведет к повреждению памяти в отладочной версии MFC. Не следует использовать перераспределение для блока памяти, выделенного **с помощью** **`new`** . Аналогично, не следует выделять блок памяти **`new`** оператором и удалять его с помощью **Free**или использовать **`delete`** оператор для блока памяти, выделенного с помощью функции **malloc**.

## <a name="see-also"></a>См. также раздел

[Управление памятью: выделение кучи](memory-management-heap-allocation.md)
