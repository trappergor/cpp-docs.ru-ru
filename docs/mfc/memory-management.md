---
title: Управление памятью | Документация Майкрософт
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
ms.openlocfilehash: 28191191572e508828a23f0e719a57d63163b08d
ms.sourcegitcommit: 9a0905c03a73c904014ec9fd3d6e59e4fa7813cd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/29/2018
ms.locfileid: "43222355"
---
# <a name="memory-management"></a>Управление памятью
Эта группа статей описывается, как пользоваться преимуществами общего назначения службы из Microsoft Foundation Class Library (MFC) связанных с управлением памятью. Выделение памяти можно разделить на две основные категории: кадров выделения и выделения памяти из кучи.  
  
 Основное различие между способами два выделения — это что с выделение кадров, которыми вы обычно работаете фактический объем памяти блок, пока с выделение кучи, всегда получают указатель на блок памяти. Другой основное отличие между двумя различными схемами является то, что объекты кадров будут автоматически удалены, пока кучи объекты должны быть явно удалены программистом.  
  
 Не MFC сведения об управлении памятью в приложениях для Windows, см. в разделе [управление памятью](https://msdn.microsoft.com/library/windows/desktop/aa366779) в пакете Windows SDK.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений  
  
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

