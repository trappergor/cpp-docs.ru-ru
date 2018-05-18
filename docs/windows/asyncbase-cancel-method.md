---
title: Метод AsyncBase::Cancel | Документы Microsoft
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
ms.openlocfilehash: 0559f32315265a7db5543e8559097177c2a670fa
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="asyncbasecancel-method"></a>Метод AsyncBase::Cancel
Отменяет асинхронную операцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDMETHOD(  
   Cancel  
)(void);  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 По умолчанию всегда возвращает значение S_OK.  
  
## <a name="remarks"></a>Примечания  
 Cancel() — это реализация по умолчанию IAsyncInfo::Cancel, а не фактический работает. Действительно отменить асинхронную операцию, переопределите OnCancel() чисто виртуального метода.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)