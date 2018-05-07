---
title: IOpenRowsetImpl::OpenRowset | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- OpenRowset
- IOpenRowsetImpl::OpenRowset
- IOpenRowsetImpl.OpenRowset
dev_langs:
- C++
helpviewer_keywords:
- OpenRowset method
ms.assetid: 2ece8d6c-d165-4f1d-b155-8609bbb60eb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 84bd34786dd87e92d70ad28d0f0a961cb01c1e48
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="iopenrowsetimplopenrowset"></a>IOpenRowsetImpl::OpenRowset
Открывает и возвращает набор строк, который содержит все строки из одной базовой таблицы или индекса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT OpenRowset(IUnknown* pUnkOuter,  
   DBID* pTableID,  
   DBID* pIndexID,  
   REFIID riid,  
   ULONG cPropertySets,  
   DBPROPSET rgPropertySets[],  
   IUnknown** ppRowset);  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [IOpenRowset::OpenRowset](https://msdn.microsoft.com/en-us/library/ms716724.aspx) в *справочника программиста OLE DB*.  
  
## <a name="remarks"></a>Примечания  
 Этот метод не найден в ATLDB. З. Она создается в мастере объектов ATL, при создании поставщика.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IOpenRowsetImpl](../../data/oledb/iopenrowsetimpl-class.md)