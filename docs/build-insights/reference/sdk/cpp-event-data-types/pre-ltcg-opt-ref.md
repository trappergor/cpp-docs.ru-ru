---
title: Класс Прелткгоптреф
description: Справочник C++ по классу SDK для Build Insights прелткгоптреф.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- PreLTCGOptRef
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 4690feddcf615a82226ce5ad2f3ee242749db04a
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334610"
---
# <a name="preltcgoptref-class"></a>Класс Прелткгоптреф

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `PreLTCGOptRef` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления [PRE_LTCG_OPT_REFного](../event-table.md#pre-ltcg-opt-ref) события.

## <a name="syntax"></a>Синтаксис

```cpp
class PreLTCGOptRef : public Activity
{
public:
    PreLTCGOptRef(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми членами от базового класса [Activity](activity.md) класс `PreLTCGOptRef` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[прелткгоптреф](#pre-ltcg-opt-ref)

## <a name="pre-ltcg-opt-ref"></a>прелткгоптреф

```cpp
PreLTCGOptRef(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [PRE_LTCG_OPT_REF](../event-table.md#pre-ltcg-opt-ref) .

::: moniker-end
