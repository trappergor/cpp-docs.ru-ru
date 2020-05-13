---
title: SimpleEvent класс
description: Ссылка на исследования в отношении СЗ Построить SDK SimpleEvent.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SimpleEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 414ff5c1af99acc612384c1ae39f6e12ab051275
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324368"
---
# <a name="simpleevent-class"></a>SimpleEvent класс

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `SimpleEvent` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его, чтобы соответствовать любому простому событию. Обратитесь к [таблице событий,](../event-table.md) чтобы просмотреть `SimpleEvent` все события, которые могут быть сопоставлены с классом.

## <a name="syntax"></a>Синтаксис

```cpp
class SimpleEvent : public Event
{
public:
    SimpleEvent(const RawEvent& event);
};
```

## <a name="members"></a>Участники

Наряду с унаследованные участники `SimpleEvent` из базового класса [Event,](event.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[SimpleEvent](#simple-event)

## <a name="simpleevent"></a><a name="simple-event"></a>SimpleEvent

```cpp
SimpleEvent(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
Любое простое событие.

::: moniker-end
