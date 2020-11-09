---
title: Класс Pass2
description: Справочник по классу Pass2 пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Pass2
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 17f915371f70a6f4398d91251680c460aa231feb
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920506"
---
# <a name="pass2-class"></a>Класс Pass2

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `Pass2` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [PASS2](../event-table.md#pass2).

## <a name="syntax"></a>Синтаксис

```cpp
class Pass2 : public LinkerPass
{
public:
    Pass2(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми элементами от базового класса [LinkerPass](linker-pass.md) класс `Pass2` включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[Pass2](#pass2)

## <a name="pass2"></a><a name="pass2"></a> Pass2

```cpp
Pass2(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [PASS2](../event-table.md#pass2).

::: moniker-end
