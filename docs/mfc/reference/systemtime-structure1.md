---
title: "Структура SYSTEMTIME | Microsoft Docs"
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
  - "SYSTEMTIME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SYSTEMTIME - структура"
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
caps.latest.revision: 15
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура SYSTEMTIME
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура `SYSTEMTIME` представляет дату и время с использованием отдельных элементов для месяца, дня, года, дня недели, часа, минуты, секунды и миллисекунды.  
  
## Синтаксис  
  
```  
  
      typedef struct _SYSTEMTIME {  
   WORD wYear;  
   WORD wMonth;  
   WORD wDayOfWeek;  
   WORD wDay;  
   WORD wHour;  
   WORD wMinute;  
   WORD wSecond;  
   WORD wMilliseconds;  
} SYSTEMTIME;  
```  
  
#### Параметры  
 *wYear*  
 Текущий год.  
  
 *wMonth*  
 Текущий месяц; январь — первый.  
  
 *wDayOfWeek*  
 Текущий день недели. воскресенье \= 0, понедельник \= 1 и т.д.  
  
 *wDay*  
 Текущие день и месяц.  
  
 *wHour*  
 Текущий час.  
  
 *wMinute*  
 Текущая минута.  
  
 *wSecond*  
 Текущая секунда.  
  
 *wMilliseconds*  
 Текущая миллисекунда.  
  
## Пример  
 [!code-cpp[NVC_MFC_Utilities#39](../../mfc/codesnippet/CPP/systemtime-structure1_1.cpp)]  
  
## Требования  
 **Заголовок:** winbase.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CTime::CTime](../Topic/CTime::CTime.md)