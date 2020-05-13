---
title: Класс PreLTCGOptRef
description: Ссылка на исследования в отношении сборки SDK PreLTCGOptRef.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- PreLTCGOptRef
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a48dc2db0345333da3ec66ccb3a345323b4f10c8
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324389"
---
# <a name="preltcgoptref-class"></a>Класс PreLTCGOptRef

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `PreLTCGOptRef` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его для соответствия [PRE_LTCG_OPT_REF](../event-table.md#pre-ltcg-opt-ref) событию.

## <a name="syntax"></a>Синтаксис

```cpp
class PreLTCGOptRef : public Activity
{
public:
    PreLTCGOptRef(const RawEvent& event);
};
```

## <a name="members"></a>Участники

Наряду с унаследованные члены `PreLTCGOptRef` из своего базового класса [деятельности,](activity.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[ПреЛТКГОпреф](#pre-ltcg-opt-ref)

## <a name="preltcgoptref"></a><a name="pre-ltcg-opt-ref"></a>ПреЛТКГОпреф

```cpp
PreLTCGOptRef(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
Событие [PRE_LTCG_OPT_REF.](../event-table.md#pre-ltcg-opt-ref)

::: moniker-end
