---
title: "CSession::GetTransactionInfo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- GetTransactionInfo
- CSession.GetTransactionInfo
- ATL.CSession.GetTransactionInfo
- CSession::GetTransactionInfo
- ATL::CSession::GetTransactionInfo
dev_langs:
- C++
helpviewer_keywords:
- GetTransactionInfo method
ms.assetid: 9fa62808-3162-4b5a-8610-e1abb8cf9a71
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 321a7980a423eade0c778d7c1b4c7ae0a12e4e7f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="csessiongettransactioninfo"></a>CSession::GetTransactionInfo
Возвращает сведения, касающиеся транзакции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp
HRESULT GetTransactionInfo(XACTTRANSINFO* pInfo) const throw();  
```  
  
#### <a name="parameters"></a>Параметры  
 В разделе [ITransaction::GetTransactionInfo](https://msdn.microsoft.com/en-us/library/ms714975.aspx) в *справочника программиста OLE DB*.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Стандартный `HRESULT`.  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [ITransaction::GetTransactionInfo](https://msdn.microsoft.com/en-us/library/ms714975.aspx) в *Справочник программиста OLE DB*.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atldbcli.h  
  
## <a name="see-also"></a>См. также  
 [Класс CSession](../../data/oledb/csession-class.md)