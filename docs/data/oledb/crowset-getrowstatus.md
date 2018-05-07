---
title: CRowset::GetRowStatus | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowset.GetRowStatus
- ATL.CRowset<TAccessor>.GetRowStatus
- ATL::CRowset<TAccessor>::GetRowStatus
- CRowset::GetRowStatus
- ATL::CRowset::GetRowStatus
- CRowset<TAccessor>::GetRowStatus
- ATL.CRowset.GetRowStatus
- CRowset<TAccessor>.GetRowStatus
- GetRowStatus
dev_langs:
- C++
helpviewer_keywords:
- GetRowStatus method
ms.assetid: 7a29a235-cb7e-40c1-92ce-5441751febee
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 3e3a0fb71a06a407a80a98717af53da926436f57
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="crowsetgetrowstatus"></a>CRowset::GetRowStatus
Возвращает состояние всех строк.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetRowStatus(DBPENDINGSTATUS* pStatus) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `pStatus`  
 [out] Указатель, по которой `GetRowStatus` возвращает значение состояния. В разделе DBPENDINGSTATUS справочника программиста OLE DB.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Этот метод требует дополнительный интерфейс `IRowsetUpdate`, который может поддерживается не всеми поставщиками; Если это так, метод возвращает **E_NOINTERFACE**. Необходимо также задать **DBPROP_IRowsetUpdate** для `VARIANT_TRUE` перед вызовом **откройте** для таблицы или команду, содержащую набор строк.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [CRowset-класс](../../data/oledb/crowset-class.md)   
 [IRowsetUpdate::GetRowStatus](https://msdn.microsoft.com/en-us/library/ms724377.aspx)