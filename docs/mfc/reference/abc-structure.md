---
title: "Структура ABC | Microsoft Docs"
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
  - "ABC"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ABC - структура"
ms.assetid: 32663839-c3b7-4f47-896c-b15329c96bc8
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура ABC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура **ABC** содержит ширину символов в шрифт TrueType.  
  
## Синтаксис  
  
```  
  
      typedef struct _ABC { /* abc */  
   int abcA;  
   UINT abcB;  
   int abcC;  
} ABC;  
```  
  
#### Параметры  
 *abcA*  
 Определяет интервал a символов.  Интервал a расстояние, добавляемого в текущей позиции перед рисования глиф символов.  
  
 *abcB*  
 Определяет размечать B символов.  Размечать B ширина вычерченной части глифов символа.  
  
 *abcC*  
 Определяет размечать C символов.  Размечать C расстояние, добавляемого в текущей позиции предоставить пробел справа от глифов символа.  
  
## Заметки  
 Полная ширина символов последовательность пробелов a, B и C.  Пробел или a и C могут быть отрицательными отображения underhangs или свисания.  
  
## Требования  
 **Header:** wingdi.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../Topic/CDC::GetCharABCWidths.md)