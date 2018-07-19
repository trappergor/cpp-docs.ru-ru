---
title: IRowsetLocateImpl::Hash | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IRowsetLocateImpl::Hash
- IRowsetLocateImpl.Hash
dev_langs:
- C++
helpviewer_keywords:
- Hash method
ms.assetid: 7df4386d-80fb-4332-a85f-baae98cdc6e0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 42076453cc8f32b56bfe354eaa2b883650d0f4f7
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33101192"
---
# <a name="irowsetlocateimplhash"></a>IRowsetLocateImpl::Hash
Возвращает хэш-значения для указанного закладки.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD (Hash )(HCHAPTER /* hReserved */,  
   DBBKMARK cbBookmarks,  
   const DBBKMARK* rgcbBookmarks[],  
   const BYTE* rgpBookmarks[],  
   DBHASHVALUE rgHashValues[],  
   DBROWSTATUS rgBookmarkStatus[]);  
```  
  
#### <a name="parameters"></a>Параметры  
 `hReserved`  
 [in] Соответствует `hChapter` параметр [IRowsetLocate::Hash](https://msdn.microsoft.com/en-us/library/ms709697.aspx).  
  
 Другие параметры в разделе [IRowsetLocate::Hash](https://msdn.microsoft.com/en-us/library/ms709697.aspx) в *Справочник программиста OLE DB*.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetLocateImpl](../../data/oledb/irowsetlocateimpl-class.md)