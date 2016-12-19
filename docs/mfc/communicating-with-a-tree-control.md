---
title: "Установка связи с древовидным элементом управления | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
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
  - "взаимодействие, элементы управления "дерево""
  - "CTreeCtrl - класс, вызов функций-членов"
  - "элементы управления "дерево""
  - "элементы управления "дерево", связь с"
ms.assetid: 680ad9ee-b11f-452d-93fa-501ca7d7e069
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Установка связи с древовидным элементом управления
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Можно использовать различные методы для вызова функции\-члены в объекте [CTreeCtrl](../mfc/reference/ctreectrl-class.md) в зависимости от того, как объект были созданы:  
  
-   Если элемент управления "Дерево" в диалоговом окне, используйте переменной\-члена типа `CTreeCtrl`, который создается в классе диалогового окна.  
  
-   Если элемент управления "Дерево" дочернее окно, используйте объект `CTreeCtrl` \(или указатель\) используется для создания объекта.  
  
-   Если используется объект `CTreeView`, используйте функцию [CTreeView::GetTreeCtrl](../Topic/CTreeView::GetTreeCtrl.md), чтобы получить ссылку на элемент управления дерева.  Можно инициализировать другую ссылку с этим значением или присвоить адрес ссылки на указатель `CTreeCtrl`.  
  
## См. также  
 [Использование CTreeCtrl](../Topic/Using%20CTreeCtrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)