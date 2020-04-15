---
title: Класс компилятора
description: Ссылка на класс SDK Compiler посборке.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Compiler
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 9b0a2622c4bc0bc19d7222977fe24c060ee8709e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325032"
---
# <a name="compiler-class"></a>Класс компилятора

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `Compiler` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его для соответствия событию [COMPILER.](../event-table.md#compiler)

## <a name="syntax"></a>Синтаксис

```cpp
class Compiler : public Invocation
{
public:
    Compiler(const RawEvent& event);
};
```

## <a name="members"></a>Участники

Наряду с унаследованных членов из `Compiler` своего базового класса [Призыв,](invocation.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[Компилятор](#compiler)

## <a name="compiler"></a><a name="compiler"></a>Компилятора

```cpp
Compiler(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
Событие [COMPILER.](../event-table.md#compiler)

::: moniker-end
