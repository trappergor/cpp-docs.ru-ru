---
title: Класс компоновщика
description: Ссылка C++ на класс компоновщика сборки Insights SDK.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Linker
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: bb8948d7772046e18d5db5002deed48d0dd88375
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334712"
---
# <a name="linker-class"></a>Класс компоновщика

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `Linker` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления с событием [компоновщика](../event-table.md#linker) .

## <a name="syntax"></a>Синтаксис

```cpp
class Linker : public Invocation
{
public:
    Linker(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Вместе с унаследованными элементами из базового класса [вызова](invocation.md) класс `Linker` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[Компоновщик](#linker)

## <a name="linker"></a>Компоновщика

```cpp
Linker(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [компоновщика](../event-table.md#linker) .

::: moniker-end
