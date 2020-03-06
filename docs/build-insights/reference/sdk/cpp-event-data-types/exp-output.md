---
title: Класс Експаутпут
description: Справочник C++ по классу SDK для Build Insights експаутпут.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ExpOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: bc108096bf2fffba876231bbf522295d0d0dcc0d
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334856"
---
# <a name="expoutput-class"></a>Класс Експаутпут

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `ExpOutput` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления с событием [EXP_OUTPUT](../event-table.md#exp-output) .

## <a name="syntax"></a>Синтаксис

```cpp
class ExpOutput : public FileOutput
{
public:
    ExpOutput(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Вместе с наследуемыми членами из своего базового класса [филеаутпут](file-output.md) класс `ExpOutput` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[експаутпут](#exp-output)

## <a name="exp-output"></a>експаутпут

```cpp
ExpOutput(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [EXP_OUTPUT](../event-table.md#exp-output) .

::: moniker-end
