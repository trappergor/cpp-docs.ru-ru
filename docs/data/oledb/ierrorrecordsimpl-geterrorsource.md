---
title: "IErrorRecordsImpl::GetErrorSource | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IErrorRecordsImpl.GetErrorSource"
  - "GetErrorSource"
  - "IErrorRecordsImpl::GetErrorSource"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetErrorSource - метод"
ms.assetid: 5436f1ce-c5a4-403b-a62b-c58e70e5c925
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IErrorRecordsImpl::GetErrorSource
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Получает исходный код, вызвавший ошибку из записи ошибок.  
  
## Синтаксис  
  
```  
  
      LPOLESTR GetErrorSource(  
   ERRORINFO& rCurError   
);  
```  
  
#### Параметры  
 `rCurError`  
 Запись `ERRORINFO` в интерфейсе **IErrorInfo**.  
  
## Возвращаемое значение  
 Указатель на строку, содержащую исходный код для ошибки.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс IErrorRecordsImpl](../../data/oledb/ierrorrecordsimpl-class.md)