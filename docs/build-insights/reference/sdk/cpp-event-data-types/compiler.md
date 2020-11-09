---
title: Класс Compiler
description: Справочник по классу Compiler пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Compiler
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 52f8bb2ffc474cbf8e58552c77a4bb9fabc13c7e
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923323"
---
# <a name="compiler-class"></a>Класс Compiler

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `Compiler` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [COMPILER](../event-table.md#compiler).

## <a name="syntax"></a>Синтаксис

```cpp
class Compiler : public Invocation
{
public:
    Compiler(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми элементами от базового класса [Invocation](invocation.md) класс `Compiler` включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[Компилятор](#compiler)

## <a name="compiler"></a><a name="compiler"></a> Compiler

```cpp
Compiler(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [COMPILER](../event-table.md#compiler).

::: moniker-end
