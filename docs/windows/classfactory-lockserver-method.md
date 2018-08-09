---
title: Метод ClassFactory::LockServer | Документация Майкрософт
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
ms.openlocfilehash: ee858346fdb70e136edfbc562c2dfffb1f63e462
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652377"
---
# <a name="classfactorylockserver-method"></a>Метод ClassFactory::LockServer
Увеличивает или уменьшает число базовых объектов, отслеживаемых текущим **ClassFactory** объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
STDMETHOD(  
   LockServer  
)(BOOL fLock);  
```  
  
### <a name="parameters"></a>Параметры  
 *fLock*  
 **значение true,** для увеличения числа отслеживаемых объектов. **false** для уменьшения числа отслеживаемых объектов.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение E_FAIL.  
  
## <a name="remarks"></a>Примечания  
 **ClassFactory** следит за объектов в базовом экземпляре класса [модуль](../windows/module-class.md) класса.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ClassFactory](../windows/classfactory-class.md)