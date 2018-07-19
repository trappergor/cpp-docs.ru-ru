---
title: IRowsetInfoImpl::GetProperties | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetInfoImpl.GetProperties
- IRowsetInfoImpl.GetProperties
- ATL::IRowsetInfoImpl::GetProperties
- IRowsetInfoImpl::GetProperties
- GetProperties
dev_langs:
- C++
helpviewer_keywords:
- GetProperties method
ms.assetid: 62c12063-28e0-4a06-ad4d-21c5c1e9ccea
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f29a9ef14c603b5a67759577a0992a1a0f70ecfa
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101283"
---
# <a name="irowsetinfoimplgetproperties"></a>IRowsetInfoImpl::GetProperties
Возвращает текущие параметры для свойств в **DBPROPSET_ROWSET** группы.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD (GetProperties )(const ULONG cPropertyIDSets,  
   const DBPROPIDSET rgPropertyIDSets[],  
   ULONG* pcPropertySets,  
   DBPROPSET** prgPropertySets);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [IRowsetInfo::GetProperties](https://msdn.microsoft.com/en-us/library/ms719611.aspx) в *справочника программиста OLE DB*.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetInfoImpl](../../data/oledb/irowsetinfoimpl-class.md)   
 [IRowsetInfoImpl::GetReferencedRowset](../../data/oledb/irowsetinfoimpl-getreferencedrowset.md)   
 [IRowsetInfoImpl::GetSpecification](../../data/oledb/irowsetinfoimpl-getspecification.md)