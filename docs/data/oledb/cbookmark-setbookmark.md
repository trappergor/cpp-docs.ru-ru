---
title: "CBookmark::SetBookmark | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CBookmark<0>::SetBookmark"
  - "ATL.CBookmark<0>.SetBookmark"
  - "CBookmark<0>.SetBookmark"
  - "SetBookmark"
  - "ATL::CBookmark::SetBookmark"
  - "ATL::CBookmark<0>::SetBookmark"
  - "CBookmark.SetBookmark"
  - "ATL.CBookmark.SetBookmark"
  - "CBookmark::SetBookmark"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetBookmark - метод"
ms.assetid: bcd26831-6045-4e69-96d6-abf8037fc18d
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CBookmark::SetBookmark
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Копирует указанное значение закладки `pBuffer` в буфер `CBookmark` и задает размер буфера в `nSize`.  
  
## Синтаксис  
  
```  
  
      HRESULT SetBookmark(  
   DBLENGTH nSize,  
   BYTE* pBuffer   
) throw( );  
```  
  
#### Параметры  
 *nSize*  
 \[in\] размер буфера закладки.  
  
 `pBuffer`  
 \[in\] указатель на массив байтов, содержащий значение закладки.  
  
## Возвращаемое значение  
 Стандартное `HRESULT`.  
  
## Заметки  
 Эта функция доступна только в **CBookmark\<0\>**.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Класс CBookmark](../../data/oledb/cbookmark-class.md)