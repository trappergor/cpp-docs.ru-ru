---
title: Метод ClassFactory::LockServer | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory::LockServer
dev_langs:
- C++
helpviewer_keywords:
- LockServer method
ms.assetid: 8d859815-956d-4f81-a5af-7cdee7e945de
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 9e09a795688c7e2b31771126f9e4036ddfbd8e4f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="classfactorylockserver-method"></a>Метод ClassFactory::LockServer
Увеличивает или уменьшает число базовых объектов, отслеживаемых текущим объектом ClassFactory.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDMETHOD(  
   LockServer  
)(BOOL fLock);  
```  
  
#### <a name="parameters"></a>Параметры  
 `fLock`  
 Значение `true` для увеличения числа отслеживаемых объектов. Значение `false` для уменьшения числа отслеживаемых объектов.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение E_FAIL.  
  
## <a name="remarks"></a>Примечания  
 ClassFactory отслеживает список объектов в базовом экземпляре класса [модуль](../windows/module-class.md) класса.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ClassFactory](../windows/classfactory-class.md)