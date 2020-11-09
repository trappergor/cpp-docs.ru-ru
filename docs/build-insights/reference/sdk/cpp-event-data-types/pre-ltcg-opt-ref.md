---
title: Класс PreLTCGOptRef
description: Справочник по классу PreLTCGOptRef пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- PreLTCGOptRef
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6786e317f0221126ec6e15c50f3fad58c5982266
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923009"
---
# <a name="preltcgoptref-class"></a>Класс PreLTCGOptRef

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `PreLTCGOptRef` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [PRE_LTCG_OPT_REF](../event-table.md#pre-ltcg-opt-ref).

## <a name="syntax"></a>Синтаксис

```cpp
class PreLTCGOptRef : public Activity
{
public:
    PreLTCGOptRef(const RawEvent& event);
};
```

## <a name="members"></a>Участники

Наряду с наследуемыми элементами от базового класса [Activity](activity.md) класс `PreLTCGOptRef` также включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[PreLTCGOptRef](#pre-ltcg-opt-ref)

## <a name="preltcgoptref"></a><a name="pre-ltcg-opt-ref"></a> PreLTCGOptRef

```cpp
PreLTCGOptRef(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [PRE_LTCG_OPT_REF](../event-table.md#pre-ltcg-opt-ref).

::: moniker-end
