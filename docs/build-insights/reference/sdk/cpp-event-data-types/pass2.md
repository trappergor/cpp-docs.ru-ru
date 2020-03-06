---
title: Класс Pass2
description: Справочник C++ по классу SDK для Build Insights Pass2.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Pass2
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 0deca0a06a74e4728cb2c78657bf5e077b42878b
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334616"
---
# <a name="pass2-class"></a>Класс Pass2

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `Pass2` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления с событием [PASS2](../event-table.md#pass2) .

## <a name="syntax"></a>Синтаксис

```cpp
class Pass2 : public LinkerPass
{
public:
    Pass2(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Вместе с наследуемыми членами из своего базового класса [линкерпасс](linker-pass.md) класс `Pass2` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[Pass2](#pass2)

## <a name="pass2"></a>Pass2

```cpp
Pass2(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [PASS2](../event-table.md#pass2) .

::: moniker-end
