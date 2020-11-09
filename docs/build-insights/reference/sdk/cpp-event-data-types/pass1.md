---
title: Класс Pass1
description: Справочник по классу Pass1 пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Pass1
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 99ada8a2db5ac464113d9805797d4b4555367e77
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923032"
---
# <a name="pass1-class"></a>Класс Pass1

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `Pass1` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [PASS1](../event-table.md#pass1).

## <a name="syntax"></a>Синтаксис

```cpp
class Pass1 : public LinkerPass
{
public:
    Pass1(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми элементами от базового класса [LinkerPass](linker-pass.md) класс `Pass1` включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[Pass1](#pass1)

## <a name="pass1"></a><a name="pass1"></a> Pass1

```cpp
Pass1(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [PASS1](../event-table.md#pass1).

::: moniker-end
