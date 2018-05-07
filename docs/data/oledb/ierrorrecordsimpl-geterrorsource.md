---
title: IErrorRecordsImpl::GetErrorSource | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- IErrorRecordsImpl.GetErrorSource
- GetErrorSource
- IErrorRecordsImpl::GetErrorSource
dev_langs:
- C++
helpviewer_keywords:
- GetErrorSource method
ms.assetid: 5436f1ce-c5a4-403b-a62b-c58e70e5c925
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f076bb7c7d436e65473aadb197a90eae51b07fd4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="ierrorrecordsimplgeterrorsource"></a>IErrorRecordsImpl::GetErrorSource
Возвращает исходный код, который вызвал ошибку из записи об ошибке.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
      LPOLESTR GetErrorSource(ERRORINFO& rCurError);  
```  
  
#### <a name="parameters"></a>Параметры  
 `rCurError`  
 `ERRORINFO` Записей в **IErrorInfo** интерфейса.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на строку, содержащие исходный код для ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldb.h  
  
## <a name="see-also"></a>См. также  
 [Класс IErrorRecordsImpl](../../data/oledb/ierrorrecordsimpl-class.md)