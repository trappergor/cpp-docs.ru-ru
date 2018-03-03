---
title: "Функция GetModuleBase | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::GetModuleBase
dev_langs:
- C++
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 19f575705b1f8680a68e9100f20be66ca22ec87a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="getmodulebase-function"></a>Функция GetModuleBase
Извлекает [ModuleBase](../windows/modulebase-class.md) указатель, который позволяет увеличивать и уменьшать счетчик ссылок [RuntimeClass](../windows/runtimeclass-class.md) объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
inline Details::ModuleBase* GetModuleBase() throw()  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на объект `ModuleBase`.  
  
## <a name="remarks"></a>Примечания  
 Эта внутренняя функция используется для увеличения и уменьшения числа ссылок объекта.  
  
 Эту функцию можно использовать для управления счетчиками ссылок путем вызова [ModuleBase::IncrementObjectCount](../windows/modulebase-incrementobjectcount-method.md) и [ModuleBase::DecrementObjectCount](../windows/modulebase-decrementobjectcount-method.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)