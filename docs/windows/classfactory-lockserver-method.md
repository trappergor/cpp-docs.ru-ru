---
title: "Метод ClassFactory::LockServer | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory::LockServer
dev_langs:
- C++
helpviewer_keywords:
- LockServer method
ms.assetid: 8d859815-956d-4f81-a5af-7cdee7e945de
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5f646f198d884e677b622a312cfdb6187802e1c6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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