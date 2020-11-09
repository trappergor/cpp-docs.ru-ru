---
title: Класс LinkerPass
description: Справочник по классу LinkerPass пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LinkerPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: bee4538ff04ec14effe0223a178ffdb2cca37a75
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920597"
---
# <a name="linkerpass-class"></a>Класс LinkerPass

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `LinkerPass` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [PASS1](../event-table.md#pass1) или [PASS2](../event-table.md#pass2).

## <a name="syntax"></a>Синтаксис

```cpp
class LinkerPass : public Activity
{
public:
    LinkerPass(const RawEvent& event);
};
```

## <a name="members"></a>Участники

Наряду с наследуемыми элементами от базового класса [Activity](activity.md) класс `LinkerPass` также включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[LinkerPass](#linker-pass)

## <a name="linkerpass"></a><a name="linker-pass"></a> LinkerPass

```cpp
LinkerPass(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [PASS1](../event-table.md#pass1) или [PASS2](../event-table.md#pass2).

::: moniker-end
