---
title: Класс Инвокатионграуп
description: Справочник C++ по классу SDK для Build Insights инвокатионграуп.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- InvocationGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b9a2bbcd2b7649b9b5703adc08ed41b272e10276
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334754"
---
# <a name="invocationgroup-class"></a>Класс Инвокатионграуп

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `InvocationGroup` используется с функциями [матчевентстакк](../functions/match-event-stack.md) и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления групп, содержащих сочетания событий [компилятора](../event-table.md#compiler) и [компоновщика](../event-table.md#linker) .

## <a name="syntax"></a>Синтаксис

```cpp
class InvocationGroup : public EventGroup<Invocation>
{
public:
    InvocationGroup(std::deque<Invocation>&& group);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми членами из своего [EventGroup\<вызова\>](event-group.md) базовым классом, класс `InvocationGroup` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[инвокатионграуп](#invocation-group)

## <a name="invocation-group"></a>инвокатионграуп

```cpp
InvocationGroup(std::deque<Invocation>&& group);
```

### <a name="parameters"></a>Параметры

\ *группы*
Группа, содержащая сочетание событий [компилятора](../event-table.md#compiler) и [компоновщика](../event-table.md#linker) .

::: moniker-end
