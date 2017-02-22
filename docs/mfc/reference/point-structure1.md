---
title: "ТОЧКА Structure1 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "POINT"
  - "LPPOINT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LPPOINT - структура"
  - "POINT - структура"
ms.assetid: 965736d8-4e53-41b6-9b8b-6961992dd21f
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# Структура POINT
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура **POINT** определяет координаты координат x и y точки.  
  
## Синтаксис  
  
```  
  
      typedef struct tagPOINT {  
   LONG x;  
   LONG y;  
} POINT;  
```  
  
#### Параметры  
 *x*  
 Задает координату x точки.  
  
 *y*  
 Задает координату y точки.  
  
## Пример  
 [!code-cpp[NVC_MFC_Utilities#37](../../mfc/codesnippet/CPP/point-structure1_1.cpp)]  
  
## Требования  
 **Header:** windef.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CPoint Class](../Topic/CPoint%20Class.md)