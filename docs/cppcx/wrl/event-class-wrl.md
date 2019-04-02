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
ms.openlocfilehash: 2d36b4fa3d1824f43e0cfafe55c439a6bdeccb6f
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58786012"
---
# <a name="event-class-wrl"></a>Класс событий (WRL)

Представляет событие.

## <a name="syntax"></a>Синтаксис

```cpp
class Event : public HandleT<HandleTraits::EventTraits>;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

name                   | Описание
---------------------- | ------------------------------------------------
[Event::Event](#event) | Инициализирует новый экземпляр класса `Event`.

### <a name="public-operators"></a>Открытые операторы

name                                 | Описание
------------------------------------ | ------------------------------------------------------------------------
[Event::operator =](#operator-assign) | Назначает указанное `Event` ссылку на текущий `Event` экземпляра.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`HandleT`

`Event`

## <a name="requirements"></a>Требования

**Заголовок:** corewrappers.h

**Пространство имен:** Microsoft::WRL::Wrappers

## <a name="event"></a>Event::Event

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

*h*<br/>
Дескриптор события. По умолчанию *h* инициализируется `nullptr`.

## <a name="operator-assign"></a>Event::operator =

Назначает указанное `Event` ссылку на текущий `Event` экземпляра.

```cpp
WRL_NOTHROW Event& operator=(
   _Inout_ Event&& h
);
```

### <a name="parameters"></a>Параметры

*h*<br/>
Ссылка rvalue на `Event` экземпляра.

### <a name="return-value"></a>Возвращаемое значение

Указатель на текущий `Event` экземпляра.
