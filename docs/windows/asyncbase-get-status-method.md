---
title: Метод AsyncBase::get_Status | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::get_Status
dev_langs:
- C++
helpviewer_keywords:
- get_Status method
ms.assetid: 9823ecb9-212e-471d-b76f-7b8f21208905
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1590d07a7b37e7dd3abf09377a03734299cb124c
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39460962"
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
 *status*  
 Расположение, где будет храниться состояние. Дополнительные сведения см. в разделе Windows::Foundation::AsyncStatus перечисления.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если выполнение прошло успешно; в противном случае E_ILLEGAL_METHOD_CALL.  
  
## <a name="remarks"></a>Примечания  
 Этот метод реализует `IAsyncInfo::get_Status`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)