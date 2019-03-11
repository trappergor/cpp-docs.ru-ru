---
title: Platform::Delegate - класс
ms.date: 12/30/2016
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Delegate
helpviewer_keywords:
- Platform::Delegate Class
ms.assetid: 82b21271-768f-4193-9ca2-be68ddfd546e
ms.openlocfilehash: 6a509827b3b8e14b6d28995b5b4ca468ee9a662e
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57741168"
---
# <a name="platformdelegate-class"></a>Platform::Delegate - класс

Представляет объект функции.

## <a name="syntax"></a>Синтаксис

```cpp
public delegate void delegate_name();
```

### <a name="members"></a>Участники

Класс Delegate имеет методы Equals(), GetHashCode() и ToString(), производные от [Platform::Object Class](../cppcx/platform-object-class.md).

### <a name="remarks"></a>Примечания

Для создания делегатов используйте ключевое слово [delegate](../windows/delegate-cpp-component-extensions.md) ; не используйте Platform::Delegate явным образом. Дополнительные сведения см. в разделе [Делегаты](../cppcx/delegates-c-cx.md). Пример создания и использования делегата см. в разделе [Creating Windows Runtime Components in C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Метаданные:** platform.winmd

## <a name="see-also"></a>См. также

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)
