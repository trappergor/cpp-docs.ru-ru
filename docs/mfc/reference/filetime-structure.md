---
title: "Структура FILETIME | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "FILETIME"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "FILETIME - структура"
ms.assetid: e09557e2-b6d7-4dd5-a5b9-6328bca88595
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 12
---
# Структура FILETIME
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура `FILETIME` 64 бит значение, представляющее число 100 интервалов наносекунды с 1\-го января 1601.  
  
## Синтаксис  
  
```  
  
      typedef struct _FILETIME {  
   DWORD dwLowDateTime;   /* low 32 bits  */  
   DWORD dwHighDateTime;  /* high 32 bits */  
} FILETIME, *PFILETIME, *LPFILETIME;  
```  
  
#### Параметры  
 *dwLowDateTime*  
 Определяет три биты 32 времени файла.  
  
 *dwHighDateTime*  
 Определяет высокие биты 32 времени файла.  
  
## Требования  
 **Header:** windef.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CTime::CTime](../Topic/CTime::CTime.md)