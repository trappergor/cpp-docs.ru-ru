---
title: Thread - класс
description: Справочник по классу Thread пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Thread
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a483536281aaa87a169a40473fe3f0c4ad10bc96
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922950"
---
# <a name="thread-class"></a>Thread - класс

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `Thread` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [THREAD](../event-table.md#thread).

## <a name="syntax"></a>Синтаксис

```cpp
class Thread : public Activity
{
public:
    Thread(const RawEvent& event);
};
```

## <a name="members"></a>Участники

Наряду с наследуемыми элементами от базового класса [Activity](activity.md) класс `Thread` также включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[Поток](#thread)

## <a name="thread"></a><a name="thread"></a> Thread

```cpp
Thread(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [THREAD](../event-table.md#thread).

::: moniker-end
