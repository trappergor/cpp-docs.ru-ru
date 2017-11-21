---
title: "IDBPropertiesImpl::GetProperties | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDBPropertiesImpl::GetProperties
- IDBPropertiesImpl.GetProperties
- GetProperties
dev_langs: C++
helpviewer_keywords: GetProperties method
ms.assetid: ab24aebd-366d-49a1-b49b-bb46c6d90f05
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6e066e525def0a983d6912774f2e27e2af045a01
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="idbpropertiesimplgetproperties"></a>IDBPropertiesImpl::GetProperties
Возвращает значения свойств источника данных, источника данных и инициализации свойства групп, заданных в настоящее время на объекте источника данных или значений свойств в группу свойств инициализации, заданных в настоящее время на перечислитель.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      STDMETHOD(GetProperties)(   
   ULONG cPropertySets,   
   const DBPROPIDSET rgPropertySets[],   
   ULONG * pcProperties,   
   DBPROPSET ** prgProperties    
);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [IDBProperties::GetProperties](https://msdn.microsoft.com/en-us/library/ms714344.aspx) в *справочника программиста OLE DB*.  
  
 Некоторые параметры соответствуют *Справочник программиста OLE DB* параметры разные имена, которые описаны в **IDBProperties::GetProperties**:  
  
|Параметры шаблонов OLE DB|*Справочник программиста OLE DB* параметров|  
|--------------------------------|------------------------------------------------|  
|`cPropertySets`|`cPropertyIDSets`|  
|`rgPropertySets`|`rgPropertyIDSets`|  
|*pcProperties*|*pcPropertySets*|  
|*prgProperties*|*prgPropertySets*|  
  
## <a name="remarks"></a>Примечания  
 При инициализации, этот метод возвращает значения свойств в **DBPROPSET_DATASOURCE**, **DBPROPSET_DATASOURCEINFO**, **DBPROPSET_DBINIT** группы свойств, заданных в настоящее время на объекте источника данных. Если поставщик не инициализирован, он возвращает **DBPROPSET_DBINIT** группы только для свойств.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IDBPropertiesImpl](../../data/oledb/idbpropertiesimpl-class.md)   
 [IDBPropertiesImpl::GetPropertyInfo](../../data/oledb/idbpropertiesimpl-getpropertyinfo.md)   
 [IDBPropertiesImpl::SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)