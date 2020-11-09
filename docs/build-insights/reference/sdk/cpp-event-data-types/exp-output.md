---
title: Класс ExpOutput
description: Справочник по классу ExpOutput пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ExpOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: f0e467466c344be0c6c796dd7cc168e6ff49d4c9
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923288"
---
# <a name="expoutput-class"></a>Класс ExpOutput

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `ExpOutput` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [EXP_OUTPUT](../event-table.md#exp-output).

## <a name="syntax"></a>Синтаксис

```cpp
class ExpOutput : public FileOutput
{
public:
    ExpOutput(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми элементами от базового класса [FileOutput](file-output.md) класс `ExpOutput` включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[ExpOutput](#exp-output)

## <a name="expoutput"></a><a name="exp-output"></a> ExpOutput

```cpp
ExpOutput(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [EXP_OUTPUT](../event-table.md#exp-output).

::: moniker-end
