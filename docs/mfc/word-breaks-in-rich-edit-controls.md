---
title: "Разбиение слов с использованием элементов управления &quot;Rich Edit&quot; | Microsoft Docs"
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
  - "разделение слов в CRichEditCtrl"
  - "CRichEditCtrl - класс, разрывы слов в"
  - "элементы управления Rich Edit, разрывы слов в"
  - "разрывы слов"
ms.assetid: 641dcf9e-7b40-4dc0-85f7-575a8c142f73
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Разбиение слов с использованием элементов управления &quot;Rich Edit&quot;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Управление расширенного редактирования \([CRichEditCtrl](../Topic/CRichEditCtrl%20Class.md)\) вызывает вызываемая функция «процедурой переноса слов» для поиска на между словами и указать, где она может линии разрыва.  Элемент управления использует их при выполнении операции перехода на новую строку и обработки сочетания клавиш CTRL \+ СТРЕЛКА ВЛЕВО и CTRL\+RIGHT.  Приложение может отправлять сообщения в элемент управления расширенного редактирования заменять процедуры переноса слов по умолчанию, извлекать сведения о переноса слов и установленную линии заданного символ находится на.  
  
## См. также  
 [Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)   
 [Элементы управления](../mfc/controls-mfc.md)