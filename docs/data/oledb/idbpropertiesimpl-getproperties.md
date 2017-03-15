---
title: "IDBPropertiesImpl::GetProperties | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IDBPropertiesImpl::GetProperties"
  - "IDBPropertiesImpl.GetProperties"
  - "GetProperties"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetProperties - метод"
ms.assetid: ab24aebd-366d-49a1-b49b-bb46c6d90f05
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# IDBPropertiesImpl::GetProperties
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Возвращает значения свойств групп свойств источника данных, данные источника данных и инициализации, которые в данный момент установлены на объект источника данных или значений свойств в группе свойств инициализации, которые в данный момент установлены на перечислитель.  
  
## Синтаксис  
  
```  
  
      STDMETHOD(GetProperties)(   
   ULONG cPropertySets,   
   const DBPROPIDSET rgPropertySets[],   
   ULONG * pcProperties,   
   DBPROPSET ** prgProperties    
);  
```  
  
#### Параметры  
 В разделе [IDBProperties::GetProperties](https://msdn.microsoft.com/en-us/library/ms714344.aspx) справочника *программиста OLE DB*.  
  
 Некоторые параметры соответствуют *параметрам ссылочным программиста OLE DB* других имен, описанных в **IDBProperties::GetProperties**:  
  
|Параметры шаблонов OLE DB|*Ссылочные параметры программиста OLE DB*|  
|-------------------------------|-----------------------------------------------|  
|`cPropertySets`|`cPropertyIDSets`|  
|`rgPropertySets`|`rgPropertyIDSets`|  
|*pcProperties*|*pcPropertySets*|  
|*prgProperties*|*prgPropertySets*|  
  
## Заметки  
 Если поставщик инициализирован, этот метод возвращает значения свойств **DBPROPSET\_DATASOURCE**, **DBPROPSET\_DATASOURCEINFO**, **DBPROPSET\_DBINIT** групп свойств, которые в данный момент установлены на объект источника данных.  Если поставщик не инициализирован, возвращается только свойства группы **DBPROPSET\_DBINIT**.  
  
## Требования  
 **Header:** atldb.h  
  
## См. также  
 [Класс IDBPropertiesImpl](../../data/oledb/idbpropertiesimpl-class.md)   
 [IDBPropertiesImpl::GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)   
 [IDBPropertiesImpl::SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)