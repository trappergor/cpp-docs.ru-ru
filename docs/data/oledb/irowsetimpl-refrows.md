---
title: "IRowsetImpl::RefRows | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::IRowsetImpl::RefRows
- ATL.IRowsetImpl.RefRows
- IRowsetImpl.RefRows
- RefRows
- IRowsetImpl::RefRows
dev_langs: C++
helpviewer_keywords: RefRows method
ms.assetid: 1c048a2a-65dc-4bba-9c81-a23c0dc249c8
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c1e39eb09ebfd3d93dd8302591db3406a8154449
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="irowsetimplrefrows"></a>IRowsetImpl::RefRows
Вызывается методом [AddRefRows](../../data/oledb/irowsetimpl-addrefrows.md) и [ReleaseRows](../../data/oledb/irowsetimpl-releaserows.md) увеличения или освободить счетчик ссылок в дескриптор существующей строки.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
      HRESULT RefRows(  
   DBCOUNTITEM cRows,  
   const HROW rghRows[],  
   DBREFCOUNT rgRefCounts[],  
   DBROWSTATUS rgRowStatus[],  
   BOOL bAdd   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [IRowset::AddRefRows](https://msdn.microsoft.com/en-us/library/ms719619.aspx) в *справочника программиста OLE DB*.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартное значение `HRESULT` .  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetImpl](../../data/oledb/irowsetimpl-class.md)   
 [Класс CSimpleRow](../../data/oledb/csimplerow-class.md)