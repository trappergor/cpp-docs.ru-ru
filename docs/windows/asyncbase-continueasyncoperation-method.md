---
title: Метод AsyncBase::ContinueAsyncOperation | Документация Майкрософт
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
ms.openlocfilehash: a335d379c1797e6152ea1b6011830423082693bb
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39648052"
---
# <a name="asyncbasecontinueasyncoperation-method"></a>Метод AsyncBase::ContinueAsyncOperation
Определяет, должны продолжать обработку асинхронной операции или следует остановить.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
inline bool ContinueAsyncOperation();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 **значение true,** Если текущее состояние асинхронной операции *работы*, который означает, что операция должна продолжаться. В противном случае **false**, который означает, что операция следует остановить.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)