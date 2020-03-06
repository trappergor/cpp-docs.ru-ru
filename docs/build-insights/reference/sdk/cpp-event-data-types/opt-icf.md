---
title: Класс Оптикф
description: Справочник C++ по классу SDK для Build Insights оптикф.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OptICF
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b7594d573a0e4eaf2e19f306b8a109923ba235dc
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334646"
---
# <a name="opticf-class"></a>Класс Оптикф

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `OptICF` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления с событием [OPT_ICF](../event-table.md#opt-icf) .

## <a name="syntax"></a>Синтаксис

```cpp
class OptICF : public Activity
{
public:
    OptICF(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми членами от базового класса [Activity](activity.md) класс `OptICF` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[оптикф](#opt-icf)

## <a name="opt-icf"></a>оптикф

```cpp
OptICF(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [OPT_ICF](../event-table.md#opt-icf) .

::: moniker-end
