---
title: "DHtmlUrlEventMapEntry Structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "DHtmlUrlEventMapEntry"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DHtmlUrlEventMapEntry - структура"
ms.assetid: 43117c1f-1a51-406c-aa2f-fea647080049
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 11
---
# DHtmlUrlEventMapEntry Structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура `DHtmlUrlEventMapEntry` обеспечивает поддержку сопоставления событий с URL\-адреса.  
  
## Синтаксис  
  
```  
  
      struct DHtmlUrlEventMapEntry  
{  
   LPCTSTR szUrl;  
   const DHtmlEventMapEntry *pEventMap;  
};  
```  
  
#### Параметры  
 `szUrl`  
 URL\-адрес.  
  
 *pEventMap*  
 Сопоставление событий, связанных с URL\-адреса.  
  
## Требования  
 **Header:** afxdhtml.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)