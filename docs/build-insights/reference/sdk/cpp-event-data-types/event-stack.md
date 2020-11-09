---
title: Класс EventStack
description: Справочник по классу EventStack пакета SDK Аналитики сборок C++.
ms.date: 02/12/2020
helpviewer_keywords:
- C++ Build Insights
- C++ Build Insights SDK
- EventStack
- throughput analysis
- build time analysis
- vcperf.exe
ms.openlocfilehash: b4f1e92011acdf8272fe631843c03c2f960a1234
ms.sourcegitcommit: 9c2b3df9b837879cd17932ae9f61cdd142078260
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "92920714"
---
# <a name="eventstack-class"></a>Класс EventStack

::: moniker range="<=msvc-140"

Пакет SDK Аналитики сборок С++ совместим с Visual Studio 2017 и более поздних версий. Чтобы увидеть документацию для этих версий, установите в данной статье селектор **Версия** Visual Studio в Visual Studio 2017 или Visual Studio 2019. Он находится в верхней части оглавления на этой странице.

::: moniker-end
::: moniker range=">=msvc-150"

Класс `EventStack` является коллекцией объектов [Event](event.md). Все события, полученные из пакета SDK Аналитики сборки C++, поступают в виде объекта `EventStack`. Последняя запись в этом стеке — это событие, обрабатываемое в данный момент. Записи, предшествующие последней записи, являются родительской иерархией текущего события. Дополнительные сведения о модели событий, используемой в Аналитике сборки C++, см. в [таблице событий](../event-table.md).

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

[EventStack](#event-stack)

### <a name="functions"></a>Функции

[Back](#back)
[operator[]](#subscript-operator)
[Size](#size)

## <a name="back"></a><a name="back"></a> Back

```cpp
RawEvent Back() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [RawEvent](raw-event.md), представляющий последнюю запись в стеке. Последняя запись в стеке событий — это активированное событие.

## <a name="eventstack"></a><a name="event-stack"></a> EventStack

```cpp
EventStack(const EVENT_COLLECTION_DATA& data);
```

### <a name="parameters"></a>Параметры

*data*\
Необработанные данные, на основе которых создается `EventStack`.

### <a name="remarks"></a>Комментарии

Обычно объекты `EventStack` не нужно создавать. Они предоставляются пакетом SDK Аналитики сборки C++ при обработке событий во время сеанса анализа или перезаписи.

## <a name="operator"></a><a name="subscript-operator"></a> operator[]

```cpp
RawEvent operator[] (size_t index) const;
```

### <a name="parameters"></a>Параметры

*index*\
Индекс элемента для доступа в стеке событий.

### <a name="return-value"></a>Возвращаемое значение

Объект [RawEvent](raw-event.md), представляющий событие, которое хранится в позиции, которую указывает *индекс* в стеке событий.

## <a name="size"></a><a name="size"></a> Размер

```cpp
size_t Size() const;
```

### <a name="return-value"></a>Возвращаемое значение

Размер стека событий.

::: moniker-end
