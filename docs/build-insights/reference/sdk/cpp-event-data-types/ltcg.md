---
title: Класс LTCG
description: Справочник C++ по классу SDK для Build Insights LTCG.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LTCG
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 8e75795e46d64752fd4d1a643585cf6f131cb096
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334676"
---
# <a name="ltcg-class"></a>Класс LTCG

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `LTCG` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления с событием [LTCG](../event-table.md#ltcg) .

## <a name="syntax"></a>Синтаксис

```cpp
class LTCG : public Activity
{
public:
    LTCG(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми членами от базового класса [Activity](activity.md) класс `LTCG` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[LTCG](#ltcg)

## <a name="ltcg"></a>LTCG

```cpp
LTCG(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [LTCG](../event-table.md#ltcg) .

::: moniker-end
