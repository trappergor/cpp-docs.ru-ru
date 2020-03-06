---
title: Класс Обжаутпут
description: Справочник C++ по классу SDK для Build Insights обжаутпут.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ObjOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 26cf110bcd086ab051174ebf0017a73370c0aa5e
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334664"
---
# <a name="objoutput-class"></a>Класс Обжаутпут

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `ObjOutput` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления с событием [OBJ_OUTPUT](../event-table.md#obj-output) .

## <a name="syntax"></a>Синтаксис

```cpp
class ObjOutput : public FileOutput
{
public:
    ObjOutput(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Вместе с наследуемыми членами из своего базового класса [филеаутпут](file-output.md) класс `ObjOutput` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[обжаутпут](#obj-output)

## <a name="obj-output"></a>обжаутпут

```cpp
ObjOutput(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [OBJ_OUTPUT](../event-table.md#obj-output) .

::: moniker-end
