---
title: Класс OptLBR
description: Справочник по классу OptLBR пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OptLBR
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5505e50b0acd961a1ff745eee36419bbaa4bd601
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923054"
---
# <a name="optlbr-class"></a>Класс OptLBR

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `OptLBR` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [OPT_LBR](../event-table.md#opt-lbr).

## <a name="syntax"></a>Синтаксис

```cpp
class OptLBR : public Activity
{
public:
    OptLBR(const RawEvent& event);
};
```

## <a name="members"></a>Участники

Наряду с наследуемыми элементами от базового класса [Activity](activity.md) класс `OptLBR` также включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[OptLBR](#opt-lbr)

## <a name="optlbr"></a><a name="opt-lbr"></a> OptLBR

```cpp
OptLBR(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [OPT_LBR](../event-table.md#opt-lbr).

::: moniker-end
