---
title: Класс функций
description: Ссылка на класс SDK Build Insights SDK.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- Function
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 69acbe4d6630de37120aec89a24a9f33d447009e
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324714"
---
# <a name="function-class"></a>Класс функций

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `Function` используется с функциями [MatchEvent,](../functions/match-event.md) [MatchEventInMemberFunction,](../functions/match-event-in-member-function.md) [MatchEventStack](../functions/match-event-stack.md)и [MatchEventStackInMemberFunction.](../functions/match-event-stack-in-member-function.md) Используйте его для соответствия событию [FUNCTION.](../event-table.md#function)

## <a name="syntax"></a>Синтаксис

```cpp
class Function : public Activity
{
public:
    Function(const RawEvent& event);

    const char* Name() const;
};
```

## <a name="members"></a>Участники

Наряду с унаследованные члены `Function` из своего базового класса [деятельности,](activity.md) класс содержит следующие члены:

### <a name="constructors"></a>Конструкторы

[Функция](#function)

### <a name="functions"></a>Функции

[имя](#name);

## <a name="function"></a><a name="function"></a>Функции

```cpp
Function(const RawEvent& event);
```

### <a name="parameters"></a>Параметры

*Событие*\
[Событие FUNCTION.](../event-table.md#function)

## <a name="name"></a><a name="name"></a>Имя

```cpp
const char* Name() const;
```

### <a name="return-value"></a>Возвращаемое значение

Название функции, закодированное в UTF-8.

::: moniker-end
