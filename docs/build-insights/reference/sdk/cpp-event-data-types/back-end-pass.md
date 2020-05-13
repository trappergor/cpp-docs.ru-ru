---
title: Класс BackEndPass
description: Ссылка на исследования sDK BackEndPass.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- BackEndPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 2b4b1a219abdbe418efaab4537f1c6dc9a22afb3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81325239"
---
# <a name="backendpass-class"></a>Класс BackEndPass

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `BackEndPass` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его для соответствия [BACK_END_PASS](../event-table.md#back-end-pass) событию.

## <a name="syntax"></a>Синтаксис

```cpp
class BackEndPass : public CompilerPass
{
public:
    BackEndPass(const RawEvent& event);
};
```

## <a name="members"></a>Участники

Наряду с унаследованных членов из `BackEndPass` своего базового класса [CompilerPass,](compiler-pass.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[BackEndPass](#back-end-pass)

## <a name="backendpass"></a><a name="back-end-pass"></a>BackEndPass

```cpp
BackEndPass(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
Событие [BACK_END_PASS.](../event-table.md#back-end-pass)

::: moniker-end
