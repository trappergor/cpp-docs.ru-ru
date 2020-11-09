---
title: Класс BottomUp
description: Справочник по классу BottomUp пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- BottomUp
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4fb5d9165837484477044f200e5a17da0e678e32
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923388"
---
# <a name="bottomup-class"></a>Класс BottomUp

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `BottomUp` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [BOTTOM_UP](../event-table.md#bottom-up).

## <a name="syntax"></a>Синтаксис

```cpp
class BottomUp : public Activity
{
public:
    BottomUp(const RawEvent& event);
};
```

## <a name="members"></a>Участники

Наряду с наследуемыми элементами от базового класса [Activity](activity.md) класс `BottomUp` также включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[BottomUp](#bottom-up)

## <a name="bottomup"></a><a name="bottom-up"></a> BottomUp

```cpp
BottomUp(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [BOTTOM_UP](../event-table.md#bottom-up).

::: moniker-end
