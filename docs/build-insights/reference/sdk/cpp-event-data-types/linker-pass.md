---
title: Класс Линкерпасс
description: Справочник C++ по классу SDK для Build Insights линкерпасс.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LinkerPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 49a46b57d82391f4c253128c14b1b81d52945eae
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334724"
---
# <a name="linkerpass-class"></a>Класс Линкерпасс

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `LinkerPass` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления с событием [PASS1](../event-table.md#pass1) или [PASS2](../event-table.md#pass2) .

## <a name="syntax"></a>Синтаксис

```cpp
class LinkerPass : public Activity
{
public:
    LinkerPass(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми членами от базового класса [Activity](activity.md) класс `LinkerPass` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[линкерпасс](#linker-pass)

## <a name="linker-pass"></a>линкерпасс

```cpp
LinkerPass(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [PASS1](../event-table.md#pass1) или [PASS2](../event-table.md#pass2) .

::: moniker-end
