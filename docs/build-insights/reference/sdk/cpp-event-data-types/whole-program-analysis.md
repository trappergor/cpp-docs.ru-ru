---
title: Класс WholeProgramAnalysis
description: Справочник по классу WholeProgramAnalysis пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- WholeProgramAnalysis
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: aa766bb33c358627d3347e1d64ed7cc3be832116
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920350"
---
# <a name="wholeprogramanalysis-class"></a>Класс WholeProgramAnalysis

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `WholeProgramAnalysis` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [WHOLE_PROGRAM_ANALYSIS](../event-table.md#whole-program-analysis).

## <a name="syntax"></a>Синтаксис

```cpp
class WholeProgramAnalysis : public Activity
{
public:
    WholeProgramAnalysis(const RawEvent& event);
};
```

## <a name="members"></a>Участники

Наряду с наследуемыми элементами от базового класса [Activity](activity.md) класс `WholeProgramAnalysis` также включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[WholeProgramAnalysis](#whole-program-analysis)

## <a name="wholeprogramanalysis"></a><a name="whole-program-analysis"></a> WholeProgramAnalysis

```cpp
WholeProgramAnalysis(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [WHOLE_PROGRAM_ANALYSIS](../event-table.md#whole-program-analysis).

::: moniker-end
