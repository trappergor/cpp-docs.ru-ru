---
title: Класс Темплатеинстантиатионграуп
description: Справочник C++ по классу SDK для Build Insights темплатеинстантиатионграуп.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TemplateInstantiationGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 281088b4c6cbd39b2fb7677180a7966b490ec3ac
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334544"
---
# <a name="templateinstantiationgroup-class"></a>Класс Темплатеинстантиатионграуп

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `TemplateInstantiationGroup` используется с функциями [матчевентстакк](../functions/match-event-stack.md) и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления групп [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) событий.

## <a name="syntax"></a>Синтаксис

```cpp
class TemplateInstantiationGroup : public EventGroup<TemplateInstantiation>
{
public:
    TemplateInstantiationGroup(std::deque<TemplateInstantiation>&& group);
};
```

## <a name="members"></a>Члены

Вместе с наследуемыми членами из его базового класса [EventGroup\<темплатеинстантиатион\>](event-group.md) класс `TemplateInstantiationGroup` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[темплатеинстантиатионграуп](#template-instantiation-group)

## <a name="template-instantiation-group"></a>темплатеинстантиатионграуп

```cpp
TemplateInstantiationGroup(std::deque<TemplateInstantiation>&& group);
```

### <a name="parameters"></a>Параметры

\ *группы*
Группа событий [TEMPLATE_INSTANTIATION](../event-table.md#template-instantiation) .

::: moniker-end
