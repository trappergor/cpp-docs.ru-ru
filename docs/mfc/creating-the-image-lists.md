---
title: "Создание списков изображений | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CListCtrl - класс, создание списков изображений для"
  - "списки изображений [C++], создание для CListCtrl"
  - "списки [C++], изображение"
ms.assetid: c2768515-deba-49e8-a6f3-5be6482afb19
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Создание списков изображений
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Создание списка изображений одинаков для [CListView](../mfc/reference/clistview-class.md) или [CListCtrl](../Topic/CListCtrl%20Class.md).  
  
> [!NOTE]
>  Нужно только списки изображений, если элемент управления содержит Список стиль `LVS_ICON`.  
  
 Используйте класс `CImageList` для создания одного или нескольких списков изображений \(для полноразмерных Значков, небольшими значками и состояний\).  В разделе [CImageList](../Topic/CImageList%20Class.md) и в разделе [Списки списка изображений](http://msdn.microsoft.com/library/windows/desktop/bb774736) в [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 Вызов [CListCtrl::SetImageList](../Topic/CListCtrl::SetImageList.md) для каждого списка изображений; передайте указатель на соответствующий объект `CImageList`.  
  
## См. также  
 [Использование CListCtrl](../Topic/Using%20CListCtrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)