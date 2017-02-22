---
title: "Потоковые операции с использованием элементов управления &quot;Rich Edit&quot; | Microsoft Docs"
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
  - "CRichEditCtrl - класс, потоковые операции"
  - "CRichEditCtrl - класс, потоковое хранение"
  - "элементы управления Rich Edit, потоковые операции"
  - "хранение, поток в CRichEditCtrl"
  - "потоковые операции в CRichEditCtrl"
  - "потоковое хранение и CRichEditCtrl"
ms.assetid: 110b4684-1e76-4ca6-9ef0-5bc8b2d93c78
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Потоковые операции с использованием элементов управления &quot;Rich Edit&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Потоки можно использовать для передачи данных в или из элемента управления расширенного редактирования \([CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md)\).  Поток определяется структурой [EDITSTREAM](http://msdn.microsoft.com/library/windows/desktop/bb787891), которая определяет буфер и определяемую приложением функцию обратного вызова.  
  
 Для считывания данных в элемент управления расширенного редактирования \(то есть в поток данных\), используйте функции\-члена [StreamIn](../Topic/CRichEditCtrl::StreamIn.md).  Элемент управления повторно вызывает приложением определенную функцию обратного вызова, которая перемещает часть данных в буфер каждый раз.  
  
 Чтобы сохранить содержимое управления расширенного редактирования \(т е потока данных out\) можно использовать функцию\-член [StreamOut](../Topic/CRichEditCtrl::StreamOut.md).  Элемент управления повторно записывается в буфер и затем вызывает приложением определенную функцию обратного вызова.  Для каждого вызова функция обратного вызова сохраняет содержимое буфера.  
  
## См. также  
 [Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)