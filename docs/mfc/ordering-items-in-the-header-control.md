---
title: "Сортировка элементов в элементе управления &quot;Заголовок&quot; | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DS_DRAGDROP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DS_DRAGDROP - уведомление"
  - "GetOrderArray - метод"
  - "элементы управления "заголовок", элементы упорядочивания"
  - "OrderToIndex - метод"
  - "последовательность"
  - "последовательность, элементы управления "заголовок""
  - "SetOrderArray - метод"
ms.assetid: 5aaef872-75b5-49c5-8fed-6f9a81fca812
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Сортировка элементов в элементе управления &quot;Заголовок&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Как только получен [добавляемые элементы в элемент управления " Заголовок "](../mfc/adding-items-to-the-header-control.md), можно изменять или получать сведения о порядке их со следующими функциями:  
  
-   [CHeaderCtrl::GetOrderArray](../Topic/CHeaderCtrl::GetOrderArray.md) [CHeaderCtrl::SetOrderArray](../Topic/CHeaderCtrl::SetOrderArray.md) и  
  
     Получает и задает слева направо порядок элементов заголовка.  
  
-   [CHeaderCtrl::OrderToIndex](../Topic/CHeaderCtrl::OrderToIndex.md).  
  
     Извлекает значение индекса для конкретного элемента заголовка.  
  
 В дополнение к предыдущим функциям элемента, стиль `HDS_DRAGDROP` позволяет пользователю перетаскиваним элементов заголовка в элементе управления " Заголовок ".  Дополнительные сведения см. в разделе [Предоставление поддержки перетаскивания элементов заголовка](../mfc/providing-drag-and-drop-support-for-header-items.md) в.  
  
## См. также  
 [Использование CHeaderCtrl](../mfc/using-cheaderctrl.md)