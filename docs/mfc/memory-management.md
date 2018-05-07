---
title: Управление памятью | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- memory [MFC]
- MFC, memory management
- memory allocation [MFC]
- memory [MFC], managing
- memory allocation [MFC], MFC
ms.assetid: 934ac81b-d630-4232-88e5-ea74f7187987
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 928a954be6a96f5026a98f724a77bebd51be27f0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="memory-management"></a>Управление памятью
Эта группа статьи описывается воспользоваться преимуществами служб общего назначения из Microsoft Foundation Class библиотеки (MFC), связанные с управлением памяти. Выделение памяти можно разделить на две основные категории: фрейма выделения и выделения кучи.  
  
 Основное различие между методы два распределения является, с выделение кадров, которые обычно работают с фактический объем памяти к блокировке, во время выделения памяти в куче, всегда получают указатель на блок памяти. Другое основное различие между двумя схемами — что кадра объектов автоматически удаляются, пока кучи объекты должны быть явно удалены программистом.  
  
 Несовместимый с MFC сведения об управлении памятью в приложениях для Windows см. в разделе [управление памятью](http://msdn.microsoft.com/library/windows/desktop/aa366779) в Windows SDK.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Выделение кадров](../mfc/memory-management-frame-allocation.md)  
  
-   [Выделение кучи](../mfc/memory-management-heap-allocation.md)  
  
-   [Выделение памяти для массива](../mfc/memory-management-examples.md)  
  
-   [Выделение памяти для массива из кучи](../mfc/memory-management-examples.md)  
  
-   [Выделение памяти для структуры данных](../mfc/memory-management-examples.md)  
  
-   [Выделение памяти для объекта](../mfc/memory-management-examples.md)  
  
-   [Изменяемые блоки памяти](../mfc/memory-management-resizable-memory-blocks.md)  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../mfc/mfc-concepts.md)   
 [Общие разделы по MFC](../mfc/general-mfc-topics.md)

