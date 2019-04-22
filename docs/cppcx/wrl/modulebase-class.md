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
ms.openlocfilehash: 254796c03d25a77da22c48881c086a41ffbfeb82
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "58785130"
---
# <a name="modulebase-class"></a>Класс ModuleBase

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
class ModuleBase;
```

## <a name="remarks"></a>Примечания

Представляет базовый класс для [модуль](module-class.md) классы.

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

name                                         | Описание
-------------------------------------------- | ---------------------------------------------------------
[ModuleBase::ModuleBase](#modulebase)        | Инициализирует экземпляр класса `Module`.
[ModuleBase:: ~ ModuleBase](#tilde-modulebase) | Деинициализирует текущий экземпляр `Module` класса.

### <a name="public-methods"></a>Открытые методы

name                                                      | Описание
--------------------------------------------------------- | -------------------------------------------------------------------------
[ModuleBase::DecrementObjectCount](#decrementobjectcount) | При реализации уменьшает число объектов, отслеживаемых модулем.
[ModuleBase::IncrementObjectCount](#incrementobjectcount) | При реализации увеличивает число объектов, отслеживаемых модулем.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ModuleBase`

## <a name="requirements"></a>Требования

**Заголовок:** implements.h

**Пространство имен:** Microsoft::WRL::Details

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
