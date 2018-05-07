---
title: CRowset::GetData | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CRowset<TAccessor>::GetData
- ATL::CRowset<TAccessor>::GetData
- ATL::CRowset::GetData
- ATL.CRowset<TAccessor>.GetData
- CRowset<TAccessor>.GetData
- CRowset::GetData
- CRowset.GetData
- ATL.CRowset.GetData
dev_langs:
- C++
helpviewer_keywords:
- GetData method [OLE DB]
ms.assetid: 1e0347b5-3e24-4ff8-a790-839616c1522f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: c0a8268f115f6c6d5a887bea7aad8a244d7e530c
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="crowsetgetdata"></a>CRowset::GetData
Извлекает данные из копии строки в наборе строк.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetData() throw();   


HRESULT GetData(int nAccessor) throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 `nAccessor`  
 [in] Номер индекса (с нуля смещение) метода доступа для доступа к данным.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Если указан метод доступа, который не является автоматическим в [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md), используйте этот метод, чтобы явным образом получать данные, передав номер доступа.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CRowset](../../data/oledb/crowset-class.md)