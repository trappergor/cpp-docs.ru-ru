---
title: "CTreeCtrl и CTreeView | Microsoft Docs"
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
  - "CTreeCtrl"
  - "CTreeView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTreeCtrl - класс, или класс CTreeView"
  - "CTreeView - класс, или класс CTreeCtrl"
  - "элементы управления "дерево", и представление в виде дерева"
  - "элементы управления представлением в виде дерева"
ms.assetid: bba5af25-103f-4b53-84d3-071bc9bd6494
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CTreeCtrl и CTreeView
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC предоставляет 2 класса, включающих управления дерева: [CTreeCtrl](../mfc/reference/ctreectrl-class.md) и [CTreeView](../mfc/reference/ctreeview-class.md).  Каждый класс полезен в различных ситуациях.  
  
 Используйте `CTreeCtrl` при необходимости простого элемента управления дочернего окна; например, в диалоговом окне.  Особенно следует использовать `CTreeCtrl` если будут другие дочерние элементы управления в окне, как в стандартном диалоговом окне.  
  
 Используйте `CTreeView`, когда требуется элемент управления "Дерево" действовать как и окно представления в документ\/представление архитектуры, так и в элементе управления дерева.  `CTreeView` займет всю клиентскую область окна\-разделителя или фреймового окна.  Она будет автоматически при изменении размера его родительское окно изменяется размер и может процесс сообщения команд из меню и сочетаний клавиш и инструментов.  Поскольку элемент управления "Дерево" содержит данные, необходимые для отображения дерева, соответствующий объект документа не должен быть сложное — можно использовать даже [CDocument](../Topic/CDocument%20Class.md) в качестве типа документа в шаблоне документов.  
  
## См. также  
 [Использование CTreeCtrl](../Topic/Using%20CTreeCtrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)