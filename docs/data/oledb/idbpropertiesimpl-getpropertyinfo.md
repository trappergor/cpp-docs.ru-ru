---
title: "IDBPropertiesImpl::GetPropertyInfo | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDBPropertiesImpl::GetPropertyInfo"
  - "IDBPropertiesImpl.GetPropertyInfo"
  - "GetPropertyInfo"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetPropertyInfo - метод"
ms.assetid: 170e9640-5010-4e0d-8a54-f50b23af08ad
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IDBPropertiesImpl::GetPropertyInfo
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает сведения о свойствах, поддерживаемых источником данных.  
  
## Синтаксис  
  
```  
  
      STDMETHOD(GetPropertyInfo)(   
   ULONG cPropertySets,   
   const DBPROPIDSET rgPropertySets[],   
   ULONG * pcPropertyInfoSets,   
   DBPROPINFOSET ** prgPropertyInfoSets,   
   OLECHAR ** ppDescBuffer    
);  
```  
  
#### Параметры  
 В разделе [IDBProperties::GetPropertyInfo](https://msdn.microsoft.com/en-us/library/ms718175.aspx) справочника *программиста OLE DB*.  
  
 Некоторые параметры соответствуют *параметрам ссылочным программиста OLE DB* других имен, описанных в **IDBProperties::GetPropertyInfo**:  
  
|Параметры шаблонов OLE DB|*Ссылочные параметры программиста OLE DB*|  
|-------------------------------|-----------------------------------------------|  
|`cPropertySets`|`cPropertyIDSets`|  
|`rgPropertySets`|`rgPropertyIDSets`|  
  
## Заметки  
 Используется [IDBInitializeImpl::m\_pCUtlPropInfo](../../data/oledb/idbinitializeimpl-m-pcutlpropinfo.md) для реализации этой функции.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс IDBPropertiesImpl](../../data/oledb/idbpropertiesimpl-class.md)   
 [IDBPropertiesImpl::GetProperties](../../data/oledb/idbpropertiesimpl-getproperties.md)   
 [IDBPropertiesImpl::SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)