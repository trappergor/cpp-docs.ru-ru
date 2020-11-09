---
title: Класс FrontEndFileGroup
description: Справочник по классу FrontEndFileGroup пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndFileGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 902b394f645030fed4eeb79bae79535e6d246a1f
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923238"
---
# <a name="frontendfilegroup-class"></a>Класс FrontEndFileGroup

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `FrontEndFileGroup` используется с функциями [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте его для сопоставления групп событий [FRONT_END_FILE](../event-table.md#front-end-file).

## <a name="syntax"></a>Синтаксис

```cpp
class FrontEndFileGroup : public EventGroup<FrontEndFile>
{
public:
    FrontEndFileGroup(std::deque<FrontEndFile>&& group);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми элементами от базового класса [EventGroup\<FrontEndFile\>](event-group.md) класс `FrontEndFileGroup` включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[FrontEndFileGroup](#front-end-file-group)

## <a name="frontendfilegroup"></a><a name="front-end-file-group"></a> FrontEndFileGroup

```cpp
FrontEndFileGroup(std::deque<FrontEndFile>&& group);
```

### <a name="parameters"></a>Параметры

*group*\
Группа событий [FRONT_END_FILE](../event-table.md#front-end-file).

::: moniker-end
