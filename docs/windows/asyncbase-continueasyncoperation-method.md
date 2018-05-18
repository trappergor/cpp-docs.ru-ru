---
title: Метод AsyncBase::ContinueAsyncOperation | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::ContinueAsyncOperation
dev_langs:
- C++
helpviewer_keywords:
- ContinueAsyncOperation method
ms.assetid: ce38181d-2fc3-4579-b0ce-237a3c7648bc
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: caf7cd1cbee97761c6877ec6ab3a51ea956cbfd1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="asyncbasecontinueasyncoperation-method"></a>Метод AsyncBase::ContinueAsyncOperation
Определяет, должны продолжать обработку асинхронной операции или следует остановить.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
inline bool ContinueAsyncOperation();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 `true` Если текущее состояние асинхронной операции *работы*, означающее операцию следует продолжить. В противном случае `false`, означающее операцию следует остановить.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)