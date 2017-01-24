---
title: "Стили окна фрейма (MFC) | Microsoft Docs"
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
  - "FWS_ADDTOTITLE"
  - "FWS_SNAPTOBARS"
  - "FWS_PREFIXTITLE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "окна фрейма, стили"
  - "FWS_ADDTOTITLE - константа"
  - "FWS_PREFIXTITLE - константа"
  - "FWS_SNAPTOBARS - константа"
  - "стили, окна"
ms.assetid: d21f270e-a088-4962-a2ae-8c03334b5a06
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Стили окна фрейма (MFC)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

-   **FWS\_ADDTOTITLE** указывает сведения для добавления в конец заголовка фреймового окна.  Например, «Microsoft paint — создать в Document1».  Можно указать отображаемые строки на вкладке строк шаблона документа в мастере приложений.  Если требуется отключить этот параметр, следует переопределить функцию\-член `CWnd::PreCreateWindow`.  
  
-   **FWS\_PREFIXTITLE** указывает имя документа перед именем приложения в заголовке фреймового окна.  Например, «document» — WordPad.  Можно указать отображаемые строки на вкладке строк шаблона документа в мастере приложений.  Если требуется отключить этот параметр, следует переопределить функцию\-член `CWnd::PreCreateWindow`.  
  
-   Изменение элементов управления **FWS\_SNAPTOBARS** фреймового окна, в которое входит панель элементов управления при ее в поле с плавающей запятой, а не закреплено в фреймовому окно.  Размер этого стиля окна в соответствии с панели элементов управления.  
  
## См. также  
 [Стили, используемые MFC](../../mfc/reference/styles-used-by-mfc.md)