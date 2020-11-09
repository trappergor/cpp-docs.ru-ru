---
title: Класс TemplateInstantiationGroup
description: Справочник по классу TemplateInstantiationGroup пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TemplateInstantiationGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: bacd48fbf15bfbbd768b527f42587425fb0932e6
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92922969"
---
# <a name="templateinstantiationgroup-class"></a>Класс TemplateInstantiationGroup

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `TemplateInstantiationGroup` используется с функциями [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления групп событий [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation).

## <a name="syntax"></a>Синтаксис

```cpp
class TemplateInstantiationGroup : public EventGroup<TemplateInstantiation>
{
public:
    TemplateInstantiationGroup(std::deque<TemplateInstantiation>&& group);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми элементами от базового класса [EventGroup\<TemplateInstantiation\>](event-group.md) класс `TemplateInstantiationGroup` включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[TemplateInstantiationGroup](#template-instantiation-group)

## <a name="templateinstantiationgroup"></a><a name="template-instantiation-group"></a> TemplateInstantiationGroup

```cpp
TemplateInstantiationGroup(std::deque<TemplateInstantiation>&& group);
```

### <a name="parameters"></a>Параметры

*group*\
Группа событий [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation).

::: moniker-end
