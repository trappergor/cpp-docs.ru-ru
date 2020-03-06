---
title: Класс Либаутпут
description: Справочник C++ по классу SDK для Build Insights либаутпут.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- LibOutput
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 9ec0d8de5302d9893aedd28661b2234150e82e08
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334736"
---
# <a name="liboutput-class"></a>Класс Либаутпут

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `LibOutput` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления [LIB_OUTPUTного](../event-table.md#lib-output) события.

## <a name="syntax"></a>Синтаксис

```cpp
class LibOutput : public FileOutput
{
public:
    LibOutput(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Вместе с наследуемыми членами из своего базового класса [филеаутпут](file-output.md) класс `LibOutput` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[либаутпут](#lib-output)

## <a name="lib-output"></a>либаутпут

```cpp
LibOutput(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [LIB_OUTPUT](../event-table.md#lib-output) .

::: moniker-end
