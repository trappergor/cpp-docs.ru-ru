---
title: Класс Форцеинлини
description: Справочник C++ по классу SDK для Build Insights форцеинлини.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- ForceInlinee
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 7d3cce13601a0b3edbcd2b57664b2d0d94a7d3df
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334838"
---
# <a name="forceinlinee-class"></a>Класс Форцеинлини

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `ForceInlinee` используется с функциями [матчевент](../functions/match-event.md), [матчевентинмемберфунктион](../functions/match-event-in-member-function.md), [матчевентстакк](../functions/match-event-stack.md)и [матчевентстаккинмемберфунктион](../functions/match-event-stack-in-member-function.md) . Используйте его для сопоставления [FORCE_INLINEEного](../event-table.md#force-inlinee) события.

## <a name="syntax"></a>Синтаксис

```cpp
class ForceInlinee : public SimpleEvent
{
public:
    ForceInlinee(const RawEvent& event);

    const char*             Name() const;
    const unsigned short&   Size() const;
};
```

## <a name="members"></a>Члены

Вместе с наследуемыми членами из своего базового класса [симпливент](simple-event.md) класс `ForceInlinee` содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[форцеинлини](#force-inlinee)

### <a name="functions"></a>Функции


[Размер](#size) [имени](#name)

## <a name="force-inlinee"></a>форцеинлини

```cpp
ForceInlinee(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*event*\
Событие [FORCE_INLINEE](../event-table.md#force-inlinee) .

## <a name="name"></a> Name

```cpp
const char* Name() const;
```

### <a name="return-value"></a>Возвращаемое значение

Имя функции принудительного встраивания в кодировке UTF-8.

## <a name="size"></a>Изменять

```cpp
const unsigned short& Size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер принудительно встроенной функции в виде промежуточного числа инструкций.

::: moniker-end
