---
title: ICommandPropertiesImpl::GetProperties | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ICommandPropertiesImpl::GetProperties
- ICommandPropertiesImpl.GetProperties
- GetProperties
dev_langs:
- C++
helpviewer_keywords:
- GetProperties method
ms.assetid: 1bee5f1b-bd08-435a-956a-e4cebcdf5d5e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4a00cac292463251b89b314e7d4bd953480c505e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33099723"
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