---
title: Класс OptICF
description: Справочник по классу OptICF пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OptICF
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b816b53e1054c4492320bdb71f2f0c7726907cf4
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920532"
---
# <a name="opticf-class"></a>Класс OptICF

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `OptICF` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [OPT_ICF](../event-table.md#opt-icf).

## <a name="syntax"></a>Синтаксис

```cpp
class OptICF : public Activity
{
public:
    OptICF(const RawEvent& event);
};
```

## <a name="members"></a>Участники

Наряду с наследуемыми элементами от базового класса [Activity](activity.md) класс `OptICF` также включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[OptICF](#opt-icf)

## <a name="opticf"></a><a name="opt-icf"></a> OptICF

```cpp
OptICF(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [OPT_ICF](../event-table.md#opt-icf).

::: moniker-end
