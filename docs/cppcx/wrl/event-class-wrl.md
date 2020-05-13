---
title: Класс событий (WRL)
ms.date: 09/24/2018
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event
- corewrappers/Microsoft::WRL::Wrappers::Event::Event
- corewrappers/Microsoft::WRL::Wrappers::Event::operator=
helpviewer_keywords:
- Microsoft::WRL::Wrappers::Event class
- Microsoft::WRL::Wrappers::Event::Event, constructor
- Microsoft::WRL::Wrappers::Event::operator= operator
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
ms.openlocfilehash: 85b4c2d1f1a27e90a65e47aa749e079f4aa08739
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81371525"
---
# <a name="event-class-wrl"></a>Класс событий (WRL)

Представляет событие.

## <a name="syntax"></a>Синтаксис

```cpp
class Event : public HandleT<HandleTraits::EventTraits>;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

Имя                   | Описание
---------------------- | ------------------------------------------------
[Событие::Событие](#event) | Инициализирует новый экземпляр класса `Event`.

### <a name="public-operators"></a>Открытые операторы

Имя                                 | Описание
------------------------------------ | ------------------------------------------------------------------------
[Событие:оператор](#operator-assign) | Назначает указанную `Event` ссылку `Event` на текущий экземпляр.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HandleT`

`Event`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft:WRL::Wrappers

## <a name="eventevent"></a><a name="event"></a>Событие::Событие

Инициализирует новый экземпляр класса `Event`.

```cpp
explicit Event(
   HANDLE h = HandleT::Traits::GetInvalidValue()
);
WRL_NOTHROW Event(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>Параметры

*H*<br/>
Дескриптор события. По *умолчанию, h* `nullptr`инициализирован до .

## <a name="eventoperator"></a><a name="operator-assign"></a>Событие:оператор

Назначает указанную `Event` ссылку `Event` на текущий экземпляр.

```cpp
WRL_NOTHROW Event& operator=(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>Параметры

*H*<br/>
Rvalue-ссылка на `Event` экземпляр.

### <a name="return-value"></a>Возвращаемое значение

Указатель на текущий `Event` экземпляр.
