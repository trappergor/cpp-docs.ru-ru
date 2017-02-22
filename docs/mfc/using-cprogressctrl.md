---
title: "Использование CProgressCtrl | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CProgressCtrl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CProgressCtrl - класс, использование"
  - "элементы управления хода выполнения [C++]"
  - "элементы управления хода выполнения [C++], CProgressCtrl"
  - "элементы управления хода выполнения [C++], использование"
ms.assetid: 61473270-196b-41ab-bf2b-467f46673539
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Использование CProgressCtrl
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Можно использовать элемент управления ходом выполнения отображения хода выполнения длительной операции.  Прямоугольник, постепенно заполняется системным цветом выделения по мере выполнения операции.  
  
 Элемент управления ходом выполнения представляется в MFC классом [CProgressCtrl](../mfc/reference/cprogressctrl-class.md).  
  
 При первоначальном создании элемент управления ходом выполнения, необходимо указать его размер и положение, родительское окно \(обычно диалоговое окно\) и идентификатор.  С помощью параметра `dwStyle`, можно задавать различные стили окна элемента управления и стили для ее заполнения.  
  
## Дополнительные сведения  
  
-   [Стили для контроля за ходом выполнения](../mfc/styles-for-the-progress-control.md)  
  
-   [Параметры для контроля за ходом выполнения](../mfc/settings-for-the-progress-control.md)  
  
-   [Управление контроль за ходом выполнения](../mfc/manipulating-the-progress-control.md)  
  
## См. также  
 [Элементы управления](../mfc/controls-mfc.md)