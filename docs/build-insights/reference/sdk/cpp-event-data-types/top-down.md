---
title: Класс Топдовн
description: Справочник C++ по классу SDK для Build Insights топдовн.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- TopDown
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2d4ef1f2f824bca9ab8e45f8fb030727e6e4007b
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334508"
---
# <a name="topdown-class"></a>Класс Топдовн

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `TopDown` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления [TOP_DOWNного](../event-table.md#top-down) события.

## <a name="syntax"></a>Синтаксис

```cpp
class TopDown : public Activity
{
public:
    TopDown(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми членами от базового класса [Activity](activity.md) класс `TopDown` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[топдовн](#top-down)

## <a name="top-down"></a>топдовн

```cpp
TopDown(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [TOP_DOWN](../event-table.md#top-down) .

::: moniker-end
