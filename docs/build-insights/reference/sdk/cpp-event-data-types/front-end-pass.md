---
title: Класс Фронтендпасс
description: Справочник C++ по классу SDK для Build Insights фронтендпасс.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- FrontEndPass
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: cc0bf38c46b51d4a49da46be88e23afa64c12cc8
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334784"
---
# <a name="frontendpass-class"></a>Класс Фронтендпасс

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `FrontEndPass` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления [FRONT_END_PASSного](../event-table.md#front-end-pass) события.

## <a name="syntax"></a>Синтаксис

```cpp
class FrontEndPass : public CompilerPass
{
public:
    FrontEndPass(const RawEvent& event);
};
```

## <a name="members"></a>Члены

Вместе с наследуемыми членами из своего базового класса [компилерпасс](compiler-pass.md) класс `FrontEndPass` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[фронтендпасс](#front-end-pass)

## <a name="front-end-pass"></a>фронтендпасс

```cpp
FrontEndPass(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [FRONT_END_PASS](../event-table.md#front-end-pass) .

::: moniker-end
