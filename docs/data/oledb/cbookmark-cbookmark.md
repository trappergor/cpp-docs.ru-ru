---
title: "CBookmark::CBookmark | Microsoft Docs"
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
  - "CBookmark<0>.CBookmark<0>"
  - "CBookmark::CBookmark"
  - "ATL.CBookmark.CBookmark"
  - "CBookmark.CBookmark"
  - "CBookmark"
  - "ATL::CBookmark<0>::CBookmark<0>"
  - "ATL.CBookmark<0>.CBookmark<0>"
  - "CBookmark<0>::CBookmark<0>"
  - "ATL::CBookmark::CBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CBookmark - класс, конструктор"
ms.assetid: 84f4ad2b-67d4-4ba3-8b2b-656a66fb6298
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CBookmark::CBookmark
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Конструктор.  
  
## Синтаксис  
  
```  
  
      CBookmark( );   
CBookmark(  
   DBLENGTH nSize   
);  
```  
  
#### Параметры  
 `nSize`  
 \[in\] размер буфера закладки в байтах.  
  
## Заметки  
 Первая функция задает буфер в **NULL** и размер буфера равным 0.  Вторая функция задает размер буфера в `nSize` и буфер байтов в массив байтов `nSize`.  
  
> [!NOTE]
>  Эта функция доступна только в **CBookmark\<0\>**.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CBookmark](../../data/oledb/cbookmark-class.md)