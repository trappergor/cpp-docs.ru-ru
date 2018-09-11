---
title: Класс Platform::Delegate | Документация Майкрософт
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Delegate
dev_langs:
- C++
helpviewer_keywords:
- Platform::Delegate Class
ms.assetid: 82b21271-768f-4193-9ca2-be68ddfd546e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 78ac7cce43dbe08097c1e7b78423fadafc7f5309
ms.sourcegitcommit: 761c5f7c506915f5a62ef3847714f43e9b815352
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/07/2018
ms.locfileid: "44101915"
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

Для создания делегатов используйте ключевое слово [delegate](../windows/delegate-cpp-component-extensions.md) ; не используйте Platform::Delegate явным образом. Дополнительные сведения см. в разделе [Делегаты](../cppcx/delegates-c-cx.md). Пример создания и использования делегата см. в разделе [создание компонентов среды выполнения Windows в C++](/windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp).

### <a name="requirements"></a>Требования

**Минимальный поддерживаемый клиент:** Windows 8

**Минимальный поддерживаемый сервер:** Windows Server 2012

**Пространство имен:** Platform

**Метаданные:** platform.winmd

## <a name="see-also"></a>См. также

[Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)