---
title: Класс TopDown
description: Справочник по классу TopDown пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TopDown
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 88622461b27a6037d8d7fbb73cd324978302c941
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920428"
---
# <a name="topdown-class"></a>Класс TopDown

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `TopDown` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [TOP_DOWN](../event-table.md#top-down).

## <a name="syntax"></a>Синтаксис

```cpp
class TopDown : public Activity
{
public:
    TopDown(const RawEvent& event);
};
```

## <a name="members"></a>Участники

Наряду с наследуемыми элементами от базового класса [Activity](activity.md) класс `TopDown` также включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[TopDown](#top-down)

## <a name="topdown"></a><a name="top-down"></a> TopDown

```cpp
TopDown(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [TOP_DOWN](../event-table.md#top-down).

::: moniker-end
