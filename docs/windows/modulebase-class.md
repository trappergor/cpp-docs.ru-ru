---
title: Класс ModuleBase
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ModuleBase
- implements/Microsoft::WRL::Details::ModuleBase::DecrementObjectCount
- implements/Microsoft::WRL::Details::ModuleBase::IncrementObjectCount
- implements/Microsoft::WRL::Details::ModuleBase::ModuleBase
- implements/Microsoft::WRL::Details::ModuleBase::~ModuleBase
helpviewer_keywords:
- ModuleBase class
- Microsoft::WRL::Details::ModuleBase::DecrementObjectCount method
- Microsoft::WRL::Details::ModuleBase::IncrementObjectCount method
- Microsoft::WRL::Details::ModuleBase::ModuleBase, constructor
- Microsoft::WRL::Details::ModuleBase::~ModuleBase, destructor
ms.assetid: edce7591-6893-46f7-94a7-382827775548
ms.openlocfilehash: 4a65b7335626cc36a4eecbe61465778889a9e7e8
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502132"
---
# <a name="modulebase-class"></a>Класс ModuleBase

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
class ModuleBase;
```

## <a name="remarks"></a>Примечания

Представляет базовый класс для [модуль](../windows/module-class.md) классы.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                                         | Описание
-------------------------------------------- | ---------------------------------------------------------
[ModuleBase::ModuleBase](#modulebase)        | Инициализирует экземпляр класса `Module`.
[ModuleBase:: ~ ModuleBase](#tilde-modulebase) | Деинициализирует текущий экземпляр `Module` класса.

### <a name="public-methods"></a>Открытые методы

Имя                                                      | Описание
--------------------------------------------------------- | -------------------------------------------------------------------------
[ModuleBase::DecrementObjectCount](#decrementobjectcount) | При реализации уменьшает число объектов, отслеживаемых модулем.
[ModuleBase::IncrementObjectCount](#incrementobjectcount) | При реализации увеличивает число объектов, отслеживаемых модулем.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ModuleBase`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::wrl:: Details

## <a name="tilde-modulebase"></a>ModuleBase:: ~ ModuleBase

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
virtual ~ModuleBase();
```

### <a name="remarks"></a>Примечания

Деинициализирует текущий экземпляр `ModuleBase` класса.

## <a name="decrementobjectcount"></a>ModuleBase::DecrementObjectCount

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
virtual long DecrementObjectCount() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Число, прежде чем операция уменьшения.

### <a name="remarks"></a>Примечания

При реализации уменьшает число объектов, отслеживаемых модулем.

## <a name="incrementobjectcount"></a>ModuleBase::IncrementObjectCount

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
virtual long IncrementObjectCount() = 0;
```

### <a name="return-value"></a>Возвращаемое значение

Счетчик перед выполнением операции инкремента.

### <a name="remarks"></a>Примечания

При реализации увеличивает число объектов, отслеживаемых модулем.

## <a name="modulebase"></a>ModuleBase::ModuleBase

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
ModuleBase();
```

### <a name="remarks"></a>Примечания

Инициализирует экземпляр класса `Module`.
