---
title: "IDBPropertiesImpl::GetPropertyInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IDBPropertiesImpl::GetPropertyInfo
- IDBPropertiesImpl.GetPropertyInfo
- GetPropertyInfo
dev_langs:
- C++
helpviewer_keywords:
- GetPropertyInfo method
ms.assetid: 170e9640-5010-4e0d-8a54-f50b23af08ad
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 257ed21b782180fbfdf9c6bec6755f178278250a
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="idbpropertiesimplgetpropertyinfo"></a>IDBPropertiesImpl::GetPropertyInfo
Возвращает сведения о свойствах, поддерживаемых источником данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD(GetPropertyInfo)(ULONG cPropertySets,   
   const DBPROPIDSET rgPropertySets[],   
   ULONG * pcPropertyInfoSets,   
   DBPROPINFOSET ** prgPropertyInfoSets,   
   OLECHAR ** ppDescBuffer);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [IDBProperties::GetPropertyInfo](https://msdn.microsoft.com/en-us/library/ms718175.aspx) в *справочника программиста OLE DB*.  
  
 Некоторые параметры соответствуют *Справочник программиста OLE DB* параметры разные имена, которые описаны в **IDBProperties::GetPropertyInfo**:  
  
|Параметры шаблонов OLE DB|*Справочник программиста OLE DB* параметров|  
|--------------------------------|------------------------------------------------|  
|`cPropertySets`|`cPropertyIDSets`|  
|`rgPropertySets`|`rgPropertyIDSets`|  
  
## <a name="remarks"></a>Примечания  
 Использует [IDBInitializeImpl::m_pCUtlPropInfo](../../data/oledb/idbinitializeimpl-m-pcutlpropinfo.md) для реализации этой функции.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IDBPropertiesImpl](../../data/oledb/idbpropertiesimpl-class.md)   
 [IDBPropertiesImpl::GetProperties](../../data/oledb/idbpropertiesimpl-getproperties.md)   
 [IDBPropertiesImpl::SetProperties](../../data/oledb/idbpropertiesimpl-setproperties.md)