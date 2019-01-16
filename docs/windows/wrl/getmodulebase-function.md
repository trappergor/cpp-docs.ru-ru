---
title: Функция GetModuleBase
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::GetModuleBase
ms.assetid: 123d3b14-2eaf-4e02-8dcd-b6567917c6a6
ms.openlocfilehash: 4d8c8467b7aeb9c21bf5f4ee19c60e6e60880688
ms.sourcegitcommit: 360b55e89e5954f494e52b1cf989fbaceda06f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "54336736"
---
# <a name="getmodulebase-function"></a>Функция GetModuleBase

Извлекает [ModuleBase](modulebase-class.md) указатель, который позволяет увеличивать и уменьшать счетчик ссылок [RuntimeClass](runtimeclass-class.md) объекта.

## <a name="syntax"></a>Синтаксис

```cpp
inline Details::ModuleBase* GetModuleBase() throw()
```

## <a name="return-value"></a>Возвращаемое значение

Указатель на объект `ModuleBase` .

## <a name="remarks"></a>Примечания

Эта внутренняя функция используется для увеличения и уменьшения числа ссылок объекта.

Эту функцию можно использовать для управления счетчиками ссылок путем вызова [ModuleBase::IncrementObjectCount](modulebase-class.md#incrementobjectcount) и [ModuleBase::DecrementObjectCount](modulebase-class.md#decrementobjectcount).

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL

## <a name="see-also"></a>См. также

[Пространство имен Microsoft::WRL](microsoft-wrl-namespace.md)