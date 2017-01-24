---
title: "Классы перетаскивания и передачи данных OLE | Microsoft Docs"
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
  - "vc.classes.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ActiveX - классы [C++]"
  - "передача данных [С++], OLE"
  - "классы передачи данных [C++]"
  - "перетаскивание [C++], классы"
  - "перетаскивание OLE [C++], и классы передачи данных"
ms.assetid: c8ab2825-ed69-4b88-8ae6-f368b94726b8
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Классы перетаскивания и передачи данных OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Эти классы используются в OLE передаче данных.  Они позволяют данные для передачи между приложениями с помощью обмена или посредством перетаскивания.  
  
 [COleDropSource](../mfc/reference/coledropsource-class.md)  
 Элементы управления операция перетаскивания a\-z.  Этот класс определяет время начала операции перетаскивания, когда действие завершено.  Он также показывает связь курсора во время операции перетаскивания.  
  
 [COleDataSource](../mfc/reference/coledatasource-class.md)  
 Используется, если приложение предоставляет данные для передачи данных.  `COleDataSource` может быть как объектно\-ориентированный представляет объект обмена.  
  
 [COleDropTarget](../Topic/COleDropTarget%20Class.md)  
 Представляет целевой объект операции перетаскивания.  Объект `COleDropTarget` соответствует окна на экране.  Определяет, является ли он принимать любые данные удалены на его и реализует фактическую операцию перетаскивания.  
  
 [COleDataObject](../mfc/reference/coledataobject-class.md)  
 Столбец используется в качестве приемника в `COleDataSource`.  объекты `COleDataObject` обеспечивают доступ к данным, который хранит объект `COleDataSource`.  
  
## См. также  
 [Общие сведения о классах](../mfc/class-library-overview.md)