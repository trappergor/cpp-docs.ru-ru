---
title: "IOpenRowsetImpl::OpenRowset | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- OpenRowset
- IOpenRowsetImpl::OpenRowset
- IOpenRowsetImpl.OpenRowset
dev_langs:
- C++
helpviewer_keywords:
- OpenRowset method
ms.assetid: 2ece8d6c-d165-4f1d-b155-8609bbb60eb6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 229f64814a86100dd016ea946dcb60488a420eb5
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
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