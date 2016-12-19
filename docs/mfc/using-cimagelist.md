---
title: "Использование CImageList | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CImageList"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CImageList - класс, использование"
  - "элемент управления списка изображений"
ms.assetid: 3d2a909e-d641-46b7-aada-81cab1a29b41
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Использование CImageList
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Список изображений, представленный классом [CImageList](../Topic/CImageList%20Class.md), коллекцию в том же измененных размер изображений, каждый из которых можно ссылаться по его индексу.  Списки изображений эффективно используются для управления большие наборы Значков или растровые изображения.  Списки изображений, нет элементов управления, поскольку они не windows; однако они используются с несколькими типами элементов управления, включая элемент управления " Список \([CListCtrl](../Topic/CListCtrl%20Class.md)\), управления дерева \([CTreeCtrl](../mfc/reference/ctreectrl-class.md)\) и элементы управления TAB \([CTabCtrl](../Topic/CTabCtrl%20Class.md)\).  
  
 Все изображения в списке изображений, содержатся в одном широком растровые изображения в формате экрана устройства.  Список изображений может также включать монохромное растровое изображение, содержащее маски, используемые для рисования изображений прозрачно \(стиль Значка\).  `CImageList` предоставляет функции\-члены, позволяющими рисовать образы, создать и удалить списки изображений, добавлять и удалять образы, заменить образы, слияние образы, и перетащить изображения.  
  
## Дополнительные сведения  
  
-   [Типы списков изображений](../Topic/Types%20of%20Image%20Lists.md)  
  
-   [С помощью списка изображений](../mfc/using-an-image-list.md)  
  
-   [Управление списки изображений](../mfc/manipulating-image-lists.md)  
  
-   [Работа с изображениями из списка изображений](../mfc/drawing-images-from-an-image-list.md)  
  
-   [Наложения изображения в списках изображений](../mfc/image-overlays-in-image-lists.md)  
  
-   [Перенос кода из списка изображений](../Topic/Dragging%20Images%20from%20an%20Image%20List.md)  
  
-   [Сведения об изображении в списках изображений](../mfc/image-information-in-image-lists.md)  
  
## См. также  
 [Элементы управления](../mfc/controls-mfc.md)