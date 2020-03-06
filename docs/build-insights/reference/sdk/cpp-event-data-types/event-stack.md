---
title: Класс Евентстакк
description: Справочник C++ по классу SDK для Build Insights евентстакк.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EventStack
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: 6da2fd25082399b82d788c5d119a39e2f7388714
ms.sourcegitcommit: 3e8fa01f323bc5043a48a0c18b855d38af3648d4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2020
ms.locfileid: "78334898"
---
# <a name="eventstack-class"></a>Класс Евентстакк

::: moniker range="<=vs-2015"

Пакет C++ SDK для Build Insights совместим с Visual Studio 2017 и более поздних версий. Чтобы просмотреть документацию по этим версиям, присвойте элементу управления "Выбор версий Visual Studio" для этой статьи значение Visual Studio 2017 или Visual Studio 2019.

::: moniker-end
::: moniker range=">=vs-2017"

Класс `EventStack` представляет собой коллекцию объектов [событий](event.md) . Все события, полученные из C++ пакета SDK для Build Insights, поступают в виде объекта `EventStack`. Последняя запись в этом стеке — это событие, обрабатываемое в данный момент. Записи, предшествующие последней записи, являются родительской иерархией текущего события. Дополнительные сведения о модели событий, используемой в C++ аналитических данных, см. в разделе [Таблица событий](../event-table.md).

## <a name="syntax"></a>Синтаксис

```cpp
class EventStack
{
public:
    EventStack(const EVENT_COLLECTION_DATA& data);

    size_t      Size() const;
    RawEvent    Back() const;
    RawEvent    operator[] (size_t index) const;
};
```

## <a name="members"></a>Члены

### <a name="constructors"></a>Конструкторы

[евентстакк](#event-stack)

### <a name="functions"></a>Функции

Оператор [Back](#back)
[[]](#subscript-operator)
[Размер](#size)

## <a name="back"></a>Назад

```cpp
RawEvent Back() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [равевент](raw-event.md) , представляющий последнюю запись в стеке. Последняя запись в стеке событий — это событие, которое было активировано.

## <a name="event-stack"></a>евентстакк

```cpp
EventStack(const EVENT_COLLECTION_DATA& data);
```

### <a name="parameters"></a>Параметры

\ *данных*
Необработанные данные, из которых строится `EventStack`.

### <a name="remarks"></a>Remarks

Обычно вам не нужно самостоятельно создавать объекты `EventStack`. Они предоставляются пакетом SDK для C++ Build Insights, когда события обрабатываются во время анализа или сеанса перезаписи в журнал.

## <a name="subscript-operator"></a>operator []

```cpp
RawEvent operator[] (size_t index) const;
```

### <a name="parameters"></a>Параметры

\ *индекса*
Индекс элемента для доступа в стеке событий.

### <a name="return-value"></a>Возвращаемое значение

Объект [равевент](raw-event.md) , представляющий событие, хранящееся в позиции, указанной в *индексе* в стеке событий.

## <a name="size"></a>Изменять

```cpp
size_t Size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер стека событий.

::: moniker-end
