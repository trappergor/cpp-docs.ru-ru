---
title: Класс WholeProgramАнализ
description: Ссылка на программу исследования SDK WholeProgramAnalysis.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- WholeProgramAnalysis
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c68441b7da09f9880bbb2f97544b1ad8da2f631f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324119"
---
# <a name="wholeprogramanalysis-class"></a>Класс WholeProgramАнализ

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `WholeProgramAnalysis` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его для соответствия [WHOLE_PROGRAM_ANALYSIS](../event-table.md#whole-program-analysis) событию.

## <a name="syntax"></a>Синтаксис

```cpp
class WholeProgramAnalysis : public Activity
{
public:
    WholeProgramAnalysis(const RawEvent& event);
};
```

## <a name="members"></a>Участники

Наряду с унаследованные члены `WholeProgramAnalysis` из своего базового класса [деятельности,](activity.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[ЦельПрограммноеАнализ](#whole-program-analysis)

## <a name="wholeprogramanalysis"></a><a name="whole-program-analysis"></a>ЦельПрограммноеАнализ

```cpp
WholeProgramAnalysis(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
Событие [WHOLE_PROGRAM_ANALYSIS.](../event-table.md#whole-program-analysis)

::: moniker-end
