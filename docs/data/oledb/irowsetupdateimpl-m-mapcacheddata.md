---
title: "IRowsetUpdateImpl::m_mapCachedData | Microsoft Docs"
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
  - "IRowsetUpdateImpl.m_mapCachedData"
  - "IRowsetUpdateImpl::m_mapCachedData"
  - "m_mapCachedData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "m_mapCachedData"
ms.assetid: 65131743-8580-48c8-bb22-68f17c9dfa13
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IRowsetUpdateImpl::m_mapCachedData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Сопоставление, содержащий исходные данные для отложенный операции.  
  
## Синтаксис  
  
```  
  
      CAtlMap<   
   HROW hRow,    
   Storage* pData   
>   
m_mapCachedData;  
```  
  
#### Параметры  
 `hRow`  
 Дескриптор строки для данных.  
  
 `pData`  
 Указатель на данные, сохраняемых.  Данные *хранилища* типа \(класс записей пользователя\).  Аргумент шаблона *хранилища* см. в разделе [Класс IRowsetUpdateImpl](../Topic/IRowsetUpdateImpl%20Class.md).  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс IRowsetUpdateImpl](../Topic/IRowsetUpdateImpl%20Class.md)