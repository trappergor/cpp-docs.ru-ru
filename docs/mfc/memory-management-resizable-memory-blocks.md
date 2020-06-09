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
ms.openlocfilehash: 74ae94146b1ec711b586ea1fecbbc89a47b40b5e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84626268"
---
# <a name="memory-management-resizable-memory-blocks"></a>Управление памятью. Изменяемые блоки памяти

Операторы **New** и **Delete** , описанные в статье [Управление памятью: примеры](memory-management-examples.md), хорошо подходят для выделения и отмены выделения блоков памяти и объектов фиксированного размера. Иногда приложению может потребоваться изменение размеров блоков памяти. Для управления блоками памяти с изменяемыми размерами в куче необходимо использовать стандартные функции библиотеки времени выполнения C: [malloc](../c-runtime-library/reference/malloc.md), [realloc](../c-runtime-library/reference/realloc.md)и [Free](../c-runtime-library/reference/free.md) .

> [!IMPORTANT]
> Смешивание операторов **New** и **Delete** с изменяемыми функциями выделения памяти в одном блоке памяти приведет к повреждению памяти в отладочной версии MFC. Не **следует использовать** перераспределение для блока памяти, выделенного с помощью **New**. Аналогично, не следует выделять блок памяти с помощью оператора **New** и удалять его с помощью **Free**или использовать оператор **Delete** для блока памяти, выделенного с помощью функции **malloc**.

## <a name="see-also"></a>См. также раздел

[Управление памятью. Выделение кучи](memory-management-heap-allocation.md)
