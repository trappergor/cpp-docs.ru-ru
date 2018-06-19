---
title: IRowsetUpdateImpl::GetOriginalData | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- ATL.IRowsetUpdateImpl.GetOriginalData
- IRowsetUpdateImpl.GetOriginalData
- GetOriginalData
- ATL::IRowsetUpdateImpl::GetOriginalData
- IRowsetUpdateImpl::GetOriginalData
dev_langs:
- C++
helpviewer_keywords:
- GetOriginalData method
ms.assetid: 7477b3b7-6b1b-49a7-8167-b34323f0fdcc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3684b9e1b7e6998d47b37d0d1a03fc08182c6a28
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33105027"
---
# <a name="irowsetupdateimplgetoriginaldata"></a>IRowsetUpdateImpl::GetOriginalData
Возвращает данные последней передачи или получена из источника данных, без учета ожидающих изменений.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      STDMETHOD (GetOriginalData )(HROW hRow,  
   HACCESSOR hAccessor,  
   void* pData);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [IRowsetUpdate::GetOriginalData](https://msdn.microsoft.com/en-us/library/ms709947.aspx) в *справочника программиста OLE DB*.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IRowsetUpdateImpl](../../data/oledb/irowsetupdateimpl-class.md)