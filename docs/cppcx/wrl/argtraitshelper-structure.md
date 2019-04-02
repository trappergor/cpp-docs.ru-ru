---
title: ArgTraitsHelper - структура
ms.date: 09/21/2018
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraitsHelper
- event/Microsoft::WRL::Details::ArgTraitsHelper::args
helpviewer_keywords:
- Microsoft::WRL::Details::ArgTraitsHelper structure
- Microsoft::WRL::Details::ArgTraitsHelper::args constant
ms.assetid: e3f798da-0aef-4a57-95d3-d38c34c47d72
ms.openlocfilehash: fbba6d96106cc95910ccd9d0029cb3e9c254d7d3
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58784984"
---
# <a name="argtraitshelper-structure"></a>ArgTraitsHelper - структура

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

## <a name="syntax"></a>Синтаксис

```cpp
template<typename TDelegateInterface>
struct ArgTraitsHelper;
```

### <a name="parameters"></a>Параметры

*TDelegateInterface*<br/>
Интерфейс делегата.

## <a name="remarks"></a>Примечания

Помогает определить общие характеристики аргументов делегата.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

name         | Описание
------------ | ------------------------------------------------------
`methodType` | Синоним для `decltype(&TDelegateInterface::Invoke)`.
`Traits`     | Синоним для `ArgTraits<methodType>`.

### <a name="public-constants"></a>Открытые константы

name                           | Описание
------------------------------ | ---------------------------------------------------------------------------------------------------------------------
[ArgTraitsHelper::args](#args) | Помогает [ArgTraits::args](#args) следить счетчик числа параметров `Invoke` метод для интерфейса делегата.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`ArgTraitsHelper`

## <a name="requirements"></a>Требования

**Заголовок:** event.h

**Пространство имен:** Microsoft::WRL::Details

## <a name="args"></a>ArgTraitsHelper::args

Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.

```cpp
static const int args = Traits::args;
```

### <a name="remarks"></a>Примечания

Помогает `ArgTraitsHelper::args` следить счетчик числа параметров `Invoke` метод для интерфейса делегата.
