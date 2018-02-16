---
title: "ICommandPropertiesImpl::GetProperties | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ICommandPropertiesImpl::GetProperties
- ICommandPropertiesImpl.GetProperties
- GetProperties
dev_langs:
- C++
helpviewer_keywords:
- GetProperties method
ms.assetid: 1bee5f1b-bd08-435a-956a-e4cebcdf5d5e
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 91b990ef20c2f9060207163093e448255287448f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="icommandpropertiesimplgetproperties"></a>ICommandPropertiesImpl::GetProperties
Возвращает все наборы запрошенного свойства, с помощью этой команды свойство схемы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD(GetProperties)(const ULONG cPropertyIDSets,   
   const DBPROPIDSET rgPropertyIDSets[],   
   ULONG * pcPropertySets,   
   DBPROPSET ** prgPropertySets);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [ICommandProperties::GetProperties](https://msdn.microsoft.com/en-us/library/ms723119.aspx) в *справочника программиста OLE DB*.  
  
## <a name="remarks"></a>Примечания  
 См. раздел [BEGIN_PROPSET_MAP](../../data/oledb/begin-propset-map.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс ICommandPropertiesImpl](../../data/oledb/icommandpropertiesimpl-class.md)   
 [ICommandPropertiesImpl::SetProperties](../../data/oledb/icommandpropertiesimpl-setproperties.md)