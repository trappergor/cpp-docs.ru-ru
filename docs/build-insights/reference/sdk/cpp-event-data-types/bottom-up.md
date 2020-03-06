---
title: Класс Боттомуп
description: Справочник C++ по классу SDK для Build Insights боттомуп.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- BottomUp
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: fa26acfdf25acc3b78de71fd21b20cbf5a0df66b
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335012"
---
# <a name="bottomup-class"></a>Класс Боттомуп

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `BottomUp` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления [BOTTOM_UPного](../event-table.md#bottom-up) события.

## <a name="syntax"></a>Синтаксис

```cpp
class BottomUp : public Activity
{
public:
    BottomUp(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми членами от базового класса [Activity](activity.md) класс `BottomUp` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[боттомуп](#bottom-up)

## <a name="bottom-up"></a>боттомуп

```cpp
BottomUp(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [BOTTOM_UP](../event-table.md#bottom-up) .

::: moniker-end
