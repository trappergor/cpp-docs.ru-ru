---
title: Класс Баккендпасс
description: Справочник C++ по классу SDK для Build Insights баккендпасс.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- BackEndPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: c159fa09b5d8a4156fc6bd886fc36da09a66db73
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78335018"
---
# <a name="backendpass-class"></a>Класс Баккендпасс

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `BackEndPass` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления [BACK_END_PASSного](../event-table.md#back-end-pass) события.

## <a name="syntax"></a>Синтаксис

```cpp
class BackEndPass : public CompilerPass
{
public:
    BackEndPass(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Вместе с наследуемыми членами из своего базового класса [компилерпасс](compiler-pass.md) класс `BackEndPass` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[баккендпасс](#back-end-pass)

## <a name="back-end-pass"></a>баккендпасс

```cpp
BackEndPass(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [BACK_END_PASS](../event-table.md#back-end-pass) .

::: moniker-end
