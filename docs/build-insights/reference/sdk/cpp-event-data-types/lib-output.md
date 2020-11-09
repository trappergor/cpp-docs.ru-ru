---
title: Класс LibOutput
description: Справочник по классу LibOutput пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LibOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7cb759403a3e9b922ffa861b3938bcb874adac32
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920623"
---
# <a name="liboutput-class"></a>Класс LibOutput

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `LibOutput` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [LIB_OUTPUT](../event-table.md#lib-output).

## <a name="syntax"></a>Синтаксис

```cpp
class LibOutput : public FileOutput
{
public:
    LibOutput(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми элементами от базового класса [FileOutput](file-output.md) класс `LibOutput` включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[LibOutput](#lib-output)

## <a name="liboutput"></a><a name="lib-output"></a> LibOutput

```cpp
LibOutput(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [LIB_OUTPUT](../event-table.md#lib-output).

::: moniker-end
