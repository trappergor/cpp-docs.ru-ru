---
title: "Структура ABCFLOAT | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ABCFLOAT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ABCFLOAT - структура"
ms.assetid: 338e7e15-9d2c-42d0-aa80-273acfde5cc5
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Структура ABCFLOAT
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура `ABCFLOAT` содержит ширины a, B и C символа шрифта.  
  
## Синтаксис  
  
```  
  
      typedef struct _ABCFLOAT { /* abcf */  
   FLOAT abcfA;  
   FLOAT abcfB;  
   FLOAT abcfC;  
} ABCFLOAT;  
```  
  
#### Параметры  
 *abcfA*  
 Определяет интервал a символов.  Интервал a расстояние, добавляемого в текущей позиции перед рисования глиф символов.  
  
 *abcfB*  
 Определяет размечать B символов.  Размечать B ширина вычерченной части глифов символа.  
  
 *abcfC*  
 Определяет размечать C символов.  Размечать C расстояние, добавляемого в текущей позиции предоставить пробел справа от глифов символа.  
  
## Заметки  
 Ширины a, B и C измерены по базовой линии шрифта.  Увеличить символов \(полная ширина символов\) количество пробелов a, B и C.  Пробел или a и C могут быть отрицательными отображения underhangs или свисания.  
  
## Требования  
 **Header:** wingdi.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GetCharABCWidths](../Topic/CDC::GetCharABCWidths.md)