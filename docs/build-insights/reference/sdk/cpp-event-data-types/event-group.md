---
title: Класс EventGroup
description: Справочник C++ по классу SDK для Build Insights EventGroup.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EventGroup
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: ac8ac70f3fc160714b86dd0c483808a4d06e7699
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334922"
---
# <a name="eventgroup-class"></a>Класс EventGroup

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Шаблон `EventGroup` класса является базовым классом для всех классов отслеживания групп.

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

*Тактивити* Тип действия, содержащийся в группе.

## <a name="members"></a>Участники

### <a name="functions"></a>Функции

[Задний](#back)
[начало](#begin)
[end](#end)
[Front](#front)
[operator []](#subscript-operator)
[Размер](#size)

## <a name="back"></a><a name="back"></a>Назад

```cpp
const TActivity& Back() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на событие последнего действия в группе.

## <a name="begin"></a><a name="begin"></a>начале

```cpp
std::deque<TActivity>::const_iterator begin() const;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на начало группы событий действия.

## <a name="end"></a><a name="end"></a>конце

```cpp
std::deque<TActivity>::const_iterator end() const;
```

### <a name="return-value"></a>Возвращаемое значение

Итератор, указывающий на одну точку после конца группы событий действий.

## <a name="front"></a><a name="front"></a>Крышку

```cpp
const TActivity& Front() const;
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на событие первого действия в группе.

## <a name="operator"></a><a name="subscript-operator"></a>operator []

```cpp
const TActivity& operator[](size_t index) const;
```

### <a name="parameters"></a>Параметры

\ *индекса*
Индекс элемента для доступа в группе событий действия.

### <a name="return-value"></a>Возвращаемое значение

Событие из стека событий, хранящегося в позиции, указанной в параметре *index*.

## <a name="size"></a><a name="size"></a>Изменять

```cpp
size_t Size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер группы событий.

::: moniker-end
