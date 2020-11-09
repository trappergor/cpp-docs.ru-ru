---
title: Класс CodeGeneration
description: Справочник по классу CodeGeneration пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CodeGeneration
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: e9d9ba3667a96c0a4fa4fe6dc76087536ef2202e
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920831"
---
# <a name="codegeneration-class"></a>Класс CodeGeneration

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `CodeGeneration` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [CODE_GENERATION](../event-table.md#code-generation).

## <a name="syntax"></a>Синтаксис

```cpp
class CodeGeneration : public Activity
{
public:
    CodeGeneration(const RawEvent& event);
};
```

## <a name="members"></a>Участники

Наряду с наследуемыми элементами от базового класса [Activity](activity.md) класс `CodeGeneration` также включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[CodeGeneration](#code-generation)

## <a name="codegeneration"></a><a name="code-generation"></a> CodeGeneration

```cpp
CodeGeneration(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [CODE_GENERATION](../event-table.md#code-generation).

::: moniker-end
