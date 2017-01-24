---
title: "Управление памятью | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "память"
  - "выделение памяти"
  - "выделение памяти, MFC - библиотека"
  - "память, управление"
  - "MFC - библиотека, управление памятью"
ms.assetid: 934ac81b-d630-4232-88e5-ea74f7187987
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Управление памятью
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эта команда в составе статьи описаны способы использования универсальных служб библиотеки Microsoft Foundation Class \(MFC\) связанного с управлением памятью.  Выделение памяти можно разделить на две основные категории: 2 выделения кадра и выделения кучи.  
  
 Одно основное различие между 2 методами, то с помощью кадра обычно работает с фактическим блоком памяти самим, а с помощью выделения кучи, всегда получает указатель на блок памяти.  Другое основное отличие между 2 схемами, объекты кадра, автоматически удаляются, а объекты кучи должны быть явно удаляются программистом.  
  
 Для данных библиотек об управлении памятью в программах для Windows см. в разделе [Управление памятью](http://msdn.microsoft.com/library/windows/desktop/aa366779) в [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Дополнительные сведения  
  
-   [Выделение кадра](../mfc/memory-management-frame-allocation.md)  
  
-   [Выделение кучи](../mfc/memory-management-heap-allocation.md)  
  
-   [Выделить память для массива](../mfc/memory-management-examples.md)  
  
-   [Отменить для массива память из кучи](../mfc/memory-management-examples.md)  
  
-   [Выделение памяти для структуры данных](../mfc/memory-management-examples.md)  
  
-   [Выделение памяти для объекта](../mfc/memory-management-examples.md)  
  
-   [Менять блоки памяти](../mfc/memory-management-resizable-memory-blocks.md)  
  
## См. также  
 [Основные понятия](../mfc/mfc-concepts.md)   
 [Общие разделы по MFC](../mfc/general-mfc-topics.md)