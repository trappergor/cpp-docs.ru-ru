---
title: "Структура MINMAXINFO | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MINMAXINFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MINMAXINFO - структура"
ms.assetid: be6fb578-f98a-4581-9ada-be9df308ed2f
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# Структура MINMAXINFO
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура `MINMAXINFO` содержит сведения о размере окна и развернутых позиции и его минимуме и размера отслеживания максимальных значений.  
  
## Синтаксис  
  
```  
  
      typedef struct tagMINMAXINFO {  
   POINT ptReserved;  
   POINT ptMaxSize;  
   POINT ptMaxPosition;  
   POINT ptMinTrackSize;  
   POINT ptMaxTrackSize;  
} MINMAXINFO;  
```  
  
#### Параметры  
 *ptReserved*  
 Зарезервировано для внутреннего использования.  
  
 *ptMaxSize*  
 Определяет развернутую \(\) point.x ширину и высоту развернутую \(point.y окна\).  
  
 `ptMaxPosition`  
 Задает положение левой части развернутого окна \(point.x\) и положение верхнего развернутого окна \(point.y\).  
  
 *ptMinTrackSize*  
 Указывает минимальную ширину отслеживания \(point.x\) и минимальную высоту отслеживания \(point.y окна\).  
  
 *ptMaxTrackSize*  
 Указывает максимальную ширину отслеживания \(point.x\) и максимальную высоту отслеживания \(point.y окна\).  
  
## Требования  
 **Header:** winuser.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnGetMinMaxInfo](../Topic/CWnd::OnGetMinMaxInfo.md)