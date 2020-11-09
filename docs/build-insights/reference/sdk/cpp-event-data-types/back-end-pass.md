---
title: Класс BackEndPass
description: Справочник по классу BackEndPass пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- BackEndPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5438fb0ae27d07cbf3f9c7ee446cd12278b4777a
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920909"
---
# <a name="backendpass-class"></a>Класс BackEndPass

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `BackEndPass` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [BACK_END_PASS](../event-table.md#back-end-pass).

## <a name="syntax"></a>Синтаксис

```cpp
class BackEndPass : public CompilerPass
{
public:
    BackEndPass(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми элементами от базового класса [CompilerPass](compiler-pass.md) класс `BackEndPass` включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[BackEndPass](#back-end-pass)

## <a name="backendpass"></a><a name="back-end-pass"></a> BackEndPass

```cpp
BackEndPass(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [BACK_END_PASS](../event-table.md#back-end-pass).

::: moniker-end
