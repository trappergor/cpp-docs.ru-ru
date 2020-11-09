---
title: Класс ObjOutput
description: Справочник по классу ObjOutput пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ObjOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 5c88ed6f1faa307d90a73104d3183adc8e50c542
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923064"
---
# <a name="objoutput-class"></a>Класс ObjOutput

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `ObjOutput` используется с функциями [MatchEvent](../functions/match-event.md), [MatchEventInMemberFunction](../functions/match-event-in-member-function.md), [MatchEventStack](../functions/match-event-stack.md) и [MatchEventStackInMemberFunction](../functions/match-event-stack-in-member-function.md). Используйте этот класс для сопоставления события [OBJ_OUTPUT](../event-table.md#obj-output).

## <a name="syntax"></a>Синтаксис

```cpp
class ObjOutput : public FileOutput
{
public:
    ObjOutput(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми элементами от базового класса [FileOutput](file-output.md) класс `ObjOutput` включает следующие элементы:

### <a name="constructors"></a>Конструкторы

[ObjOutput](#obj-output)

## <a name="objoutput"></a><a name="obj-output"></a> ObjOutput

```cpp
ObjOutput(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [OBJ_OUTPUT](../event-table.md#obj-output).

::: moniker-end
