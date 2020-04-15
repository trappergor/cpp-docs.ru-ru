---
title: Класс TemplateInstantiationGroup
description: Ссылка на исследования в отношении справок о сборке SDK TemplateInstantiationGroup.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TemplateInstantiationGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 18dd48219c7c68ce152c381eb505fe37b19ec8dd
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324259"
---
# <a name="templateinstantiationgroup-class"></a>Класс TemplateInstantiationGroup

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `TemplateInstantiationGroup` используется с функциями [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его для сопоставления групп [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) событий.

## <a name="syntax"></a>Синтаксис

```cpp
class TemplateInstantiationGroup : public EventGroup<TemplateInstantiation>
{
public:
    TemplateInstantiationGroup(std::deque<TemplateInstantiation>&& group);
};
```

## <a name="members"></a>Участники

Наряду с унаследованных членов из своего класса `TemplateInstantiationGroup` [Исходная группа\<TemplateInstantiation,\> ](event-group.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[TemplateInstantiationGroup](#template-instantiation-group)

## <a name="templateinstantiationgroup"></a><a name="template-instantiation-group"></a>TemplateInstantiationGroup

```cpp
TemplateInstantiationGroup(std::deque<TemplateInstantiation>&& group);
```

### <a name="parameters"></a>Параметры

*Группы*\
Группа [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) событий.

::: moniker-end
