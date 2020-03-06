---
title: Класс стратегию
description: Справочник C++ по классу SDK для Build Insights стратегию.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- CodeGeneration
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 1bc56794a197b9ae7bf116757581fb5a49699462
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334964"
---
# <a name="codegeneration-class"></a>Класс стратегию

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `CodeGeneration` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления [CODE_GENERATIONного](../event-table.md#code-generation) события.

## <a name="syntax"></a>Синтаксис

```cpp
class CodeGeneration : public Activity
{
public:
    CodeGeneration(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Наряду с наследуемыми членами от базового класса [Activity](activity.md) класс `CodeGeneration` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[Стратегию](#code-generation)

## <a name="code-generation"></a>Стратегию

```cpp
CodeGeneration(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [CODE_GENERATION](../event-table.md#code-generation) .

::: moniker-end
