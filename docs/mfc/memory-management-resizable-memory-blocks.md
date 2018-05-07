---
title: 'Управление памятью: Изменяемые блоки памяти | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory blocks [MFC], resizable
- memory [MFC], corruption
- memory allocation [MFC], memory block size
- memory blocks [MFC], allocating
- blocks [MFC], memory allocation
- resizable memory blocks [MFC]
ms.assetid: f0efe6f4-a3ed-4541-9195-51ec1291967a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3bbd97899261f85454824fcab261d330b04e25fd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="memory-management-resizable-memory-blocks"></a>Управление памятью. Изменяемые блоки памяти
**Новый** и **удаление** операторы, описанные в статье [управление памятью: примеры](../mfc/memory-management-examples.md), хорошо подходят для выделение и освобождение блоков фиксированного размера памяти и объекты. В некоторых случаях приложение может понадобиться изменяемые блоки памяти. Необходимо использовать стандартные функции библиотеки времени выполнения C [malloc](../c-runtime-library/reference/malloc.md), [realloc](../c-runtime-library/reference/realloc.md), и [свободного](../c-runtime-library/reference/free.md) для управления изменяемые блоки памяти в куче.  
  
> [!IMPORTANT]
>  Смешивание **новый** и **удалить** операторы с функциями с раскрывающимися списками выделения памяти на том же блоке памяти приведет к повреждение памяти в отладочной версии MFC. Не следует использовать `realloc` на блок памяти, выделенной с помощью **новый**. Аналогичным образом, не следует выделить блок памяти с **новый** оператор и удалите его с **свободного**, или используйте **удалить** оператора в блок памяти, выделенной с `malloc`.  
  
## <a name="see-also"></a>См. также  
 [Управление памятью. Выделение кучи](../mfc/memory-management-heap-allocation.md)

