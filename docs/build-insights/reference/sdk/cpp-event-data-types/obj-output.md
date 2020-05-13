---
title: Класс ObjOutput
description: Ссылка на класс SDK ObjOutput.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ObjOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 194253e8995401114e2529b868b36c9823510a4f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324494"
---
# <a name="objoutput-class"></a>Класс ObjOutput

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `ObjOutput` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его для соответствия [OBJ_OUTPUT](../event-table.md#obj-output) событию.

## <a name="syntax"></a>Синтаксис

```cpp
class ObjOutput : public FileOutput
{
public:
    ObjOutput(const RawEvent& event);
};
```

## <a name="members"></a>Участники

Наряду с унаследованных членов из `ObjOutput` своего базового класса [FileOutput,](file-output.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[ObjOutput](#obj-output)

## <a name="objoutput"></a><a name="obj-output"></a>ObjOutput

```cpp
ObjOutput(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
[Событие OBJ_OUTPUT.](../event-table.md#obj-output)

::: moniker-end
