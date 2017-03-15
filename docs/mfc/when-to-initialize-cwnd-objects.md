---
title: "Время инициализации объектов CWnd | Microsoft Docs"
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
  - "CWnd-объекты, если HWND прикреплен"
  - "CWnd-объекты, когда инициализировать"
  - "HWND, если прикреплено к объекту CWnd"
  - "инициализация объектов CWnd"
  - "инициализация объектов, CWnd"
  - "объекты окон, когда инициализировать CWnd"
ms.assetid: 4d31bcb1-73db-4f2f-b71c-89b087569a10
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Время инициализации объектов CWnd
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Можно создать собственные дочерние окна или вызывать какие\-либо функции API Windows в конструкторе `CWnd`\- производного объекта.  Это происходит потому, что `HWND` для объекта `CWnd` не была создана.  Большинство инициализацию Windows\- функции, например добавьте дочерние окна, должны выполняться в обработчике сообщений [OnCreate](../Topic/CWnd::OnCreate.md).  
  
## Дополнительные сведения  
  
-   [Создание фреймы окна документа](../Topic/Creating%20Document%20Frame%20Windows.md)  
  
-   [Создание документов и представлений](../mfc/document-view-creation.md)  
  
## См. также  
 [Использование окон фрейма](../Topic/Using%20Frame%20Windows.md)