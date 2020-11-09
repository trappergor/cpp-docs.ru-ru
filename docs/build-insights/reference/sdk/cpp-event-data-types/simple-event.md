---
title: Класс SimpleEvent
description: Справочник по классу SimpleEvent пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SimpleEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: dc09a279157482089adedc660395feaa98376dae
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922996"
---
# <a name="simpleevent-class"></a>Класс SimpleEvent

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `SimpleEvent` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Этот класс используется для сопоставления любого простого события. Чтобы просмотреть все события, которые можно сопоставить с помощью класса `SimpleEvent`, см. [таблицу событий](../event-table.md).

## <a name="syntax"></a>Синтаксис

```cpp
class SimpleEvent : public Event
{
public:
    SimpleEvent(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми элементами от базового класса [Event](event.md) класс `SimpleEvent` включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[SimpleEvent](#simple-event)

## <a name="simpleevent"></a><a name="simple-event"></a> SimpleEvent

```cpp
SimpleEvent(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Любое простое событие.

::: moniker-end
