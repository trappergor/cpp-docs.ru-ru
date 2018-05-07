---
title: CSession::Abort | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-data
ms.topic: reference
f1_keywords:
- CSession.Abort
- CSession::Abort
- ATL.CSession.Abort
- ATL::CSession::Abort
dev_langs:
- C++
helpviewer_keywords:
- Abort method
ms.assetid: 02413b20-c486-451f-b4d7-73a6e8065df8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 8b4789db8497f314c19eb531327f4b712f37fc5e
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="csessionabort"></a>CSession::Abort
Завершает транзакцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT Abort(BOID* pboidReason = NULL,   
   BOOL bRetaining = FALSE,   
   BOOL bAsync = FALSE) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [ITransaction::Abort](https://msdn.microsoft.com/en-us/library/ms709833.aspx) в *справочника программиста OLE DB*.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CSession](../../data/oledb/csession-class.md)