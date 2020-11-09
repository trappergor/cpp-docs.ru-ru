---
title: Класс FrontEndPass
description: Справочник по классу FrontEndPass пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c2959b1b80163819287b1907c9d25ca75aa5bbc2
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923210"
---
# <a name="frontendpass-class"></a>Класс FrontEndPass

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `FrontEndPass` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [FRONT_END_PASS](../event-table.md#front-end-pass).

## <a name="syntax"></a>Синтаксис

```cpp
class FrontEndPass : public CompilerPass
{
public:
    FrontEndPass(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми элементами от базового класса [CompilerPass](compiler-pass.md) класс `FrontEndPass` включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[FrontEndPass](#front-end-pass)

## <a name="frontendpass"></a><a name="front-end-pass"></a> FrontEndPass

```cpp
FrontEndPass(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [FRONT_END_PASS](../event-table.md#front-end-pass).

::: moniker-end
