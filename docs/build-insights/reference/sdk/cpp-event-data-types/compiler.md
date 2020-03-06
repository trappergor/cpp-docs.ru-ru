---
title: Класс компилятора
description: Справочник C++ по классу компилятора SDK для аналитики сборки.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Compiler
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: a63a0bad1ab6063d5986fec77b5135f500ded1ce
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334946"
---
# <a name="compiler-class"></a>Класс компилятора

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `Compiler` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления с событием [компилятора](../event-table.md#compiler) .

## <a name="syntax"></a>Синтаксис

```cpp
class Compiler : public Invocation
{
public:
    Compiler(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Вместе с унаследованными элементами из базового класса [вызова](invocation.md) класс `Compiler` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[Компилятора](#compiler)

## <a name="compiler"></a>Компилятора

```cpp
Compiler(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [компилятора](../event-table.md#compiler) .

::: moniker-end
