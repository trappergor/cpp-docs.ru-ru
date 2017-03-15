---
title: "IRowsetImpl::GetData | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL.IRowsetImpl.GetData"
  - "ATL::IRowsetImpl::GetData"
  - "IRowsetImpl::GetData"
  - "IRowsetImpl.GetData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetData - метод [OLE DB]"
ms.assetid: cb15f1cc-bd25-4b74-93c3-db71aa93829c
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# IRowsetImpl::GetData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Извлекает данные из копии набора строк для строки.  
  
## Синтаксис  
  
```  
  
      STDMETHOD( GetData )(  
   HROW hRow,  
   HACCESSOR hAccessor,  
   void* pDstData   
);  
```  
  
#### Параметры  
 В разделе [IRowset::GetData](https://msdn.microsoft.com/en-us/library/ms716988.aspx) справочника *программиста OLE DB*.  
  
 Некоторые параметры соответствуют *параметрам ссылочным программиста OLE DB* других имен, описанных в **IRowset::GetData**:  
  
|Параметры шаблонов OLE DB|*Ссылочные параметры программиста OLE DB*|  
|-------------------------------|-----------------------------------------------|  
|*pDstData*|`pData`|  
  
## Заметки  
 Также выполняет преобразование данных с использованием библиотеки DLL преобразования данных OLE DB.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс IRowsetImpl](../Topic/IRowsetImpl%20Class.md)