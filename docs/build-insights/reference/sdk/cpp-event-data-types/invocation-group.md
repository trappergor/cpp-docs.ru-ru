---
title: Класс InvocationGroup
description: Справочник по классу InvocationGroup пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- InvocationGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1a8d4786a228ab25551ee36ce22637d44dc07307
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920636"
---
# <a name="invocationgroup-class"></a>Класс InvocationGroup

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `InvocationGroup` используется с функциями [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте его для сопоставления групп, содержащих сочетание событий [COMPILER](../event-table.md#compiler) и [LINKER](../event-table.md#linker).

## <a name="syntax"></a>Синтаксис

```cpp
class InvocationGroup : public EventGroup<Invocation>
{
public:
    InvocationGroup(std::deque<Invocation>&& group);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми элементами от базового класса [EventGroup\<Invocation\>](event-group.md) класс `InvocationGroup` включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[InvocationGroup](#invocation-group)

## <a name="invocationgroup"></a><a name="invocation-group"></a> InvocationGroup

```cpp
InvocationGroup(std::deque<Invocation>&& group);
```

### <a name="parameters"></a>Параметры

*group*\
Группа, содержащая сочетание событий [COMPILER](../event-table.md#compiler) и [LINKER](../event-table.md#linker).

::: moniker-end
