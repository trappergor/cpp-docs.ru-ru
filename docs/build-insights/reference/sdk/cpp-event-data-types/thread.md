---
title: Thread - класс
description: Справочник C++ по классу потока SDK для аналитики сборки.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Thread
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a74eb130bd3f8be949fef0c19d545f61a72f3934
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334520"
---
# <a name="thread-class"></a>Thread - класс

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `Thread` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления с событием [потока](../event-table.md#thread) .

## <a name="syntax"></a>Синтаксис

```cpp
class Thread : public Activity
{
public:
    Thread(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми членами от базового класса [Activity](activity.md) класс `Thread` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[Поток](#thread)

## <a name="thread"></a>Поток

```cpp
Thread(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [потока](../event-table.md#thread) .

::: moniker-end
