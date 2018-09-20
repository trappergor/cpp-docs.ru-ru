---
title: Функция GetModuleBase | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::GetModuleBase
dev_langs:
- C++
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4d460b006d2d17df308a62c0433621aac7008f4d
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46411421"
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