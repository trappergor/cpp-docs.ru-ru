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
ms.openlocfilehash: b048b60a5512ecc54750cb980ca67e2373e2c837
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364778"
---
# <a name="memory-management-resizable-memory-blocks"></a>Управление памятью. Изменяемые блоки памяти

**Новые** и **удалить** операторов, описанные в статье [Управление памятью: Примеры](../mfc/memory-management-examples.md), хороши для распределения и решения блоков памяти фиксированного размера и объектов. Иногда вашему приложению могут понадобиться изменяемые блоки памяти. Вы должны использовать стандартные C запустить время библиотеки функции [malloc,](../c-runtime-library/reference/malloc.md) [realloc](../c-runtime-library/reference/realloc.md), и [бесплатно](../c-runtime-library/reference/free.md) управлять измеримых блоков памяти на куче.

> [!IMPORTANT]
> Смешивание **новых** операторов и **удаление** операторов с функциями распределения изыски памяти на одном блоке памяти приведет к повреждению памяти в версии Debug MFC. Не следует использовать **realloc** на блоке памяти, выделенном **новым.** Кроме того, вы не должны выделять блок памяти с **новым** оператором и удалить его **бесплатно,** или использовать **оператора удаления** на блок е,5, выделенном с **malloc.**

## <a name="see-also"></a>См. также раздел

[Управление памятью. Выделение кучи](../mfc/memory-management-heap-allocation.md)
