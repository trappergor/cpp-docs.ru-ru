---
title: Класс Вхолепрограманалисис
description: Справочник C++ по классу SDK для Build Insights вхолепрограманалисис.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- WholeProgramAnalysis
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6b8e41242acb9e902b250bab960b1c2042dd981a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334496"
---
# <a name="wholeprogramanalysis-class"></a>Класс Вхолепрограманалисис

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `WholeProgramAnalysis` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления [WHOLE_PROGRAM_ANALYSISного](../event-table.md#whole-program-analysis) события.

## <a name="syntax"></a>Синтаксис

```cpp
class WholeProgramAnalysis : public Activity
{
public:
    WholeProgramAnalysis(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми членами от базового класса [Activity](activity.md) класс `WholeProgramAnalysis` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[вхолепрограманалисис](#whole-program-analysis)

## <a name="whole-program-analysis"></a>вхолепрограманалисис

```cpp
WholeProgramAnalysis(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [WHOLE_PROGRAM_ANALYSIS](../event-table.md#whole-program-analysis) .

::: moniker-end
