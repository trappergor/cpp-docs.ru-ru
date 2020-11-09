---
title: Класс ImpLibOutput
description: Справочник по классу ImpLibOutput пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ImpLibOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 01adb0041a3d212acf1bb846ced9019600016cda
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923182"
---
# <a name="impliboutput-class"></a>Класс ImpLibOutput

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `ImpLibOutput` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [IMP_LIB_OUTPUT](../event-table.md#imp-lib-output).

## <a name="syntax"></a>Синтаксис

```cpp
class ImpLibOutput : public FileOutput
{
public:
    ImpLibOutput(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми элементами от базового класса [FileOutput](file-output.md) класс `ImpLibOutput` включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[ImpLibOutput](#imp-lib-output)

## <a name="impliboutput"></a><a name="imp-lib-output"></a> ImpLibOutput

```cpp
ImpLibOutput(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [IMP_LIB_OUTPUT](../event-table.md#imp-lib-output).

::: moniker-end
