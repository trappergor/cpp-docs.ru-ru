---
title: Класс EventGroup
description: Справочник по классу EventGroup пакета SDK для C++ Build Insights.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EventGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 57cbc7a053132909149aee182b9560e2ee33c161
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92923306"
---
# <a name="eventgroup-class"></a>Класс EventGroup

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Шаблон класса `EventGroup` — это базовый класс для всех классов отслеживания групп.

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

*TActivity*  — это тип действия, содержащийся в группе.

## <a name="members"></a>Члены

### <a name="functions"></a>Функции

[Back](#back)
[begin](#begin)
[end](#end)
[Front](#front)
[operator[]](#subscript-operator)
[Size](#size)

## <a name="back"></a><a name="back"></a> Back

```cpp
const TActivity& Back() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на последнее событие действия в группе.

## <a name="begin"></a><a name="begin"></a> begin

```cpp
std::deque<TActivity>::const_iterator begin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на начало группы событий действий.

## <a name="end"></a><a name="end"></a> end

```cpp
std::deque<TActivity>::const_iterator end() const;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на одну позицию после окончания группы событий действий.

## <a name="front"></a><a name="front"></a> Front

```cpp
const TActivity& Front() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на первое событие действия в группе.

## <a name="operator"></a><a name="subscript-operator"></a> operator[]

```cpp
const TActivity& operator[](size_t index) const;
```

### <a name="parameters"></a>Параметры

*index*\
Индекс элемента для доступа в группе событий действия.

### <a name="return-value"></a>Возвращаемое значение

Событие из стека событий, хранящегося в позиции, которая указана в *индексе*.

## <a name="size"></a><a name="size"></a> Размер

```cpp
size_t Size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер группы событий.

::: moniker-end
