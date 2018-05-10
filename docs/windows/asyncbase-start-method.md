---
title: Метод AsyncBase::Start | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Start
dev_langs:
- C++
helpviewer_keywords:
- Start method
ms.assetid: 67405c9d-0d1a-4c1e-8ea4-6ba01c1f90d9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0acc6f62530daf641a2e4d568ed511d6fd831c20
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="asyncbasestart-method"></a>Метод AsyncBase::Start
Начинает асинхронную операцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDMETHOD(  
   Start  
)(void);  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция начинается или уже запущен; в противном случае E_ILLEGAL_STATE_CHANGE.  
  
## <a name="remarks"></a>Примечания  
 Start() IAsyncInfo::Start это реализация по умолчанию, а не фактический работает. Чтобы фактически запускает асинхронную операцию, переопределите OnStart() чисто виртуального метода.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)