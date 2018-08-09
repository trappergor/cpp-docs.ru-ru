---
title: Метод AsyncBase::Cancel | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Cancel
dev_langs:
- C++
helpviewer_keywords:
- Cancel method
ms.assetid: 8bfebc63-3848-4629-bc89-aa538ed7e7ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 439a118bbea5adce4c306298e573bed85da26291
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641908"
---
# <a name="asyncbasecancel-method"></a>Метод AsyncBase::Cancel
Отменяет асинхронную операцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
STDMETHOD(  
   Cancel  
)(void);  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 По умолчанию всегда возвращает значение S_OK.  
  
## <a name="remarks"></a>Примечания  
 **Cancel()** — это реализация по умолчанию `IAsyncInfo::Cancel`, а не фактические работает. Действительно отменить асинхронную операцию, переопределить `OnCancel()` чисто виртуального метода.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)