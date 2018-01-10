---
title: "Метод AsyncBase::get_Status | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::get_Status
dev_langs: C++
helpviewer_keywords: get_Status method
ms.assetid: 9823ecb9-212e-471d-b76f-7b8f21208905
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: aaa51225f8ff4ec81fbfa549b00f3614c0ad7c9d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbasegetstatus-method"></a>Метод AsyncBase::get_Status
Получает значение, указывающее состояние асинхронной операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDMETHOD(  
   get_Status  
)(AsyncStatus *status) override;  
```  
  
#### <a name="parameters"></a>Параметры  
 `status`  
 Расположение, где будет храниться состояние. Дополнительные сведения см. в разделе Windows::Foundation::AsyncStatus перечисления.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если успешно; в противном случае E_ILLEGAL_METHOD_CALL.  
  
## <a name="remarks"></a>Примечания  
 Этот метод реализует IAsyncInfo::get_Status.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)