---
title: Класс C2DLL
description: Справочник по классу C2DLL пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- C2DLL
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 81aa4722d918646a0275099879bfee567ebc8f22
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923380"
---
# <a name="c2dll-class"></a>Класс C2DLL

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `C2DLL` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [C2_DLL](../event-table.md#c2-dll).

## <a name="syntax"></a>Синтаксис

```cpp
class C2DLL : public Activity
{
public:
    C2DLL(const RawEvent& event);
};
```

## <a name="members"></a>Участники

Наряду с наследуемыми элементами от базового класса [Activity](activity.md) класс `C2DLL` также включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[C2DLL](#c2-dll)

## <a name="c2dll"></a><a name="c2-dll"></a> C2DLL

```cpp
C2DLL(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [C2_DLL](../event-table.md#c2-dll).

::: moniker-end
