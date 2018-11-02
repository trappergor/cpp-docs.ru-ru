---
title: Функция GetModuleBase
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::GetModuleBase
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
ms.openlocfilehash: 40289903eba2ce7ac35d4d0b208c3b609efb09f2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50650818"
---
# <a name="getmodulebase-function"></a>Функция GetModuleBase
Извлекает [ModuleBase](../windows/modulebase-class.md) указатель, который позволяет увеличивать и уменьшать счетчик ссылок [RuntimeClass](../windows/runtimeclass-class.md) объекта.

## <a name="syntax"></a>Синтаксис

```cpp
inline Details::ModuleBase* GetModuleBase() throw()
```

## <a name="return-value"></a>Возвращаемое значение

Указатель на объект `ModuleBase` .

## <a name="remarks"></a>Примечания

Эта внутренняя функция используется для увеличения и уменьшения числа ссылок объекта.

Эту функцию можно использовать для управления счетчиками ссылок путем вызова [ModuleBase::IncrementObjectCount](../windows/modulebase-incrementobjectcount-method.md) и [ModuleBase::DecrementObjectCount](../windows/modulebase-decrementobjectcount-method.md).

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)