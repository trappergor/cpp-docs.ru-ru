---
title: Класс Оптреф
description: Справочник C++ по классу SDK для Build Insights оптреф.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- OptRef
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c2abad6489012250862bc0721663572d03261bd4
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334640"
---
# <a name="optref-class"></a>Класс Оптреф

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `OptRef` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления с событием [OPT_REF](../event-table.md#opt-ref) .

## <a name="syntax"></a>Синтаксис

```cpp
class OptRef : public Activity
{
public:
    OptRef(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми членами от базового класса [Activity](activity.md) класс `OptRef` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[оптреф](#opt-ref)

## <a name="opt-ref"></a>оптреф

```cpp
OptRef(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [OPT_REF](../event-table.md#opt-ref) .

::: moniker-end
