---
title: Метод AsyncBase::CurrentStatus | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::CurrentStatus
dev_langs:
- C++
helpviewer_keywords:
- CurrentStatus method
ms.assetid: 26ee4c4a-6525-4a5f-b49c-3ca40c365eb6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 36c3f76e3fc137458acddacd834563d845057a24
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646579"
---
# <a name="asyncbasecurrentstatus-method"></a>Метод AsyncBase::CurrentStatus
Извлекает состояние текущей асинхронной операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
inline void CurrentStatus(  
   Details::AsyncStatusInternal *status  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *status*  
 Расположение, в котором эта операция сохраняет текущее состояние.  
  
## <a name="remarks"></a>Примечания  
 Данная операция является потокобезопасной.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Asyncbase-класс](../windows/asyncbase-class.md)   
 [Перечисление AsyncStatusInternal](../windows/asyncstatusinternal-enumeration.md)