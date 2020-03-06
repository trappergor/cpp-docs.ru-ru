---
title: Класс Симпливент
description: Справочник C++ по классу SDK для Build Insights симпливент.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- SimpleEvent
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4c30f81236138328322d8c870d4ad69d9988b49a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334592"
---
# <a name="simpleevent-class"></a>Класс Симпливент

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `SimpleEvent` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления с любым простым событием. Чтобы просмотреть все события, которые могут быть сопоставлены с классом `SimpleEvent`, см. [таблицу событий](../event-table.md) .

## <a name="syntax"></a>Синтаксис

```cpp
class SimpleEvent : public Event
{
public:
    SimpleEvent(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Вместе с унаследованными членами из базового класса [событий](event.md) класс `SimpleEvent` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[симпливент](#simple-event)

## <a name="simple-event"></a>симпливент

```cpp
SimpleEvent(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Любое простое событие.

::: moniker-end
