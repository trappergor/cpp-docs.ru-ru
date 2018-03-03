---
title: "Управление памятью: Изменяемые блоки памяти | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3fce06d27a091ad1740c882367358cf69a6dc3e0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="memory-management-resizable-memory-blocks"></a>Управление памятью. Изменяемые блоки памяти
**Новый** и **удаление** операторы, описанные в статье [управление памятью: примеры](../mfc/memory-management-examples.md), хорошо подходят для выделение и освобождение блоков фиксированного размера памяти и объекты. В некоторых случаях приложение может понадобиться изменяемые блоки памяти. Необходимо использовать стандартные функции библиотеки времени выполнения C [malloc](../c-runtime-library/reference/malloc.md), [realloc](../c-runtime-library/reference/realloc.md), и [свободного](../c-runtime-library/reference/free.md) для управления изменяемые блоки памяти в куче.  
  
> [!IMPORTANT]
>  Смешивание **новый** и **удалить** операторы с функциями с раскрывающимися списками выделения памяти на том же блоке памяти приведет к повреждение памяти в отладочной версии MFC. Не следует использовать `realloc` на блок памяти, выделенной с помощью **новый**. Аналогичным образом, не следует выделить блок памяти с **новый** оператор и удалите его с **свободного**, или используйте **удалить** оператора в блок памяти, выделенной с `malloc`.  
  
## <a name="see-also"></a>См. также  
 [Управление памятью. Выделение кучи](../mfc/memory-management-heap-allocation.md)

