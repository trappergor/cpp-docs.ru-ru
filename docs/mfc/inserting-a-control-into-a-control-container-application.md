---
title: "Контейнеры элементов управления ActiveX. Вставка элемента управления в приложение контейнера элемента управления | Microsoft Docs"
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
  - "контейнер для элементов ActiveX [C++], вставка элементов управления"
  - "элементы управления ActiveX [C++], добавление в проекты"
ms.assetid: bbb617ff-872f-43d8-b4d6-c49adb16b148
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Контейнеры элементов управления ActiveX. Вставка элемента управления в приложение контейнера элемента управления
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Перед получением доступа к элемента управления ActiveX с приложения контейнера элементов управления ActiveX, необходимо добавить элемент управления ActiveX в приложение\-контейнеру с помощью диалогового окна [Вставить элемент ActiveX](../Topic/Insert%20ActiveX%20Control%20Dialog%20Box.md).  
  
 Чтобы добавить элемент управления ActiveX в проект контейнера элементов управления ActiveX см. в разделе [Просмотр и добавление элементов управления ActiveX в диалоговое окно](../mfc/viewing-and-adding-activex-controls-to-a-dialog-box.md).  
  
 После добавления элемента управления необходимо добавить переменную\-член типа \(элемент управления ActiveX\) к классу диалогового окна.  Дополнительные сведения об этой процедуре см. в разделе [Добавление переменной\-члена](../ide/adding-a-member-variable-visual-cpp.md).  
  
 После добавления переменной\-члена класс, который класс\-оболочка, автоматически создается и добавляется в проект.  Этот класс используется как интерфейс между контейнером элементов управления и внедренным элементом управления.  
  
## См. также  
 [Контейнеры для элементов управления ActiveX](../mfc/activex-control-containers.md)