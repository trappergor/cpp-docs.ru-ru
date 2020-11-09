---
title: Класс LTCG
description: Справочник по классу LTCG пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LTCG
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 3b6bab629307c9fc4fb021df2e75772d5247566d
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920558"
---
# <a name="ltcg-class"></a>Класс LTCG

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `LTCG` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [LTCG](../event-table.md#ltcg).

## <a name="syntax"></a>Синтаксис

```cpp
class LTCG : public Activity
{
public:
    LTCG(const RawEvent& event);
};
```

## <a name="members"></a>Участники

Наряду с наследуемыми элементами от базового класса [Activity](activity.md) класс `LTCG` также включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[LTCG](#ltcg)

## <a name="ltcg"></a><a name="ltcg"></a> LTCG

```cpp
LTCG(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [LTCG](../event-table.md#ltcg).

::: moniker-end
