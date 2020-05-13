---
title: Класс EventGroup
description: Ссылка на класс SDK EventGroup по сборке.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EventGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 596c18ca0e9b4d7b26c4ed5209b16871952c4af2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81324986"
---
# <a name="eventgroup-class"></a>Класс EventGroup

::: moniker range="<=vs-2015"

SDK Build Insights совместим с Visual Studio 2017 и выше. Чтобы увидеть документацию для этих версий, установите элемент управления **селектора** визуальной версии для этой статьи на Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части таблицы содержимого на этой странице.

::: moniker-end
::: moniker range=">=vs-2017"

Шаблон `EventGroup` класса является базовым классом для всех классов группового захвата.

## <a name="syntax"></a>Синтаксис

```cpp
template <typename TActivity>
class EventGroup;
{
public:
    size_t Size() const;

    const TActivity& operator[](size_t index) const;
    const TActivity& Front() const;
    const TActivity& Back() const;

    std::deque<TActivity>::const_iterator begin() const;
    std::deque<TActivity>::const_iterator end() const;
};
```

### <a name="parameters"></a>Параметры

*TActivity* Тип действия, содержащийся в группе.

## <a name="members"></a>Участники

### <a name="functions"></a>Функции

[Назад](#back)
[начать](#begin)
[конец](#end)
Фронт[оператора](#front)
[»](#subscript-operator)
[Размер](#size)

## <a name="back"></a><a name="back"></a>Назад

```cpp
const TActivity& Back() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на последнее событие активности в группе.

## <a name="begin"></a><a name="begin"></a>Начать

```cpp
std::deque<TActivity>::const_iterator begin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор указывает на начало группы событий активности.

## <a name="end"></a><a name="end"></a>Конец

```cpp
std::deque<TActivity>::const_iterator end() const;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий одну позицию мимо конца группы событий активности.

## <a name="front"></a><a name="front"></a>Перед

```cpp
const TActivity& Front() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на первое событие активности в группе.

## <a name="operator"></a><a name="subscript-operator"></a>оператор

```cpp
const TActivity& operator[](size_t index) const;
```

### <a name="parameters"></a>Параметры

*Индекс*\
Индекс элемента для доступа в группе событий активности.

### <a name="return-value"></a>Возвращаемое значение

Событие из стека событий хранится в позиции, указанной *индексом.*

## <a name="size"></a><a name="size"></a> Размер

```cpp
size_t Size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер группы событий.

::: moniker-end
