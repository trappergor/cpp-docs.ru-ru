---
title: "Роль просмотра при печати | Microsoft Docs"
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
  - "CView - класс, роль в печати"
  - "OnDraw - метод, и печать"
  - "печать [MFC], OnDraw - метод"
  - "печать [MFC], представления"
  - "представления печати"
  - "представления, печать"
ms.assetid: 8d4a3c8e-1fce-4edc-b608-94cb5f3e487e
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Роль просмотра при печати
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представления также играет роль в 2 важных ввести его связанный документ.  
  
 Представление:  
  
-   Использует тот же код [OnDraw](../Topic/CView::OnDraw.md) для рисования на принтере о рисовании на экране.  
  
-   Manages разделяя документ в страницы для печати.  
  
 Дополнительные сведения о печати и роли представления в печати см. в разделе [Печать и предварительный просмотр](../mfc/printing-and-print-preview.md).  
  
## См. также  
 [Использование представлений](../mfc/using-views.md)