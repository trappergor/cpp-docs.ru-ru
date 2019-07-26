---
title: Класс time_point
ms.date: 03/27/2019
f1_keywords:
- chrono/std::chrono::time_point
- chrono/std::chrono::time_point::time_point
- chrono/std::chrono::time_point::max
- chrono/std::chrono::time_point::min
- chrono/std::chrono::time_point::time_since_epoch
ms.assetid: 18be1e52-57b9-489a-8a9b-f58894f0aaad
helpviewer_keywords:
- std::chrono [C++], time_point
ms.openlocfilehash: 4511c7b2d8629f1a052137c7997daf5913c976ab
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459991"
---
# <a name="timepoint-class"></a>Класс time_point

`time_point` описывает тип, представляющий момент времени. Он содержит объект типа [duration](../standard-library/duration-class.md), в котором хранится время, прошедшее с начала эпохи, представленной аргументом шаблона `Clock`.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Clock,
    class Duration = typename Clock::duration>
class time_point;
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|name|Описание|
|----------|-----------------|
|`time_point::clock`|Синоним параметра шаблона `Clock`.|
|`time_point::duration`|Синоним параметра шаблона `Duration`.|
|`time_point::period`|Синоним имени вложенного типа `duration::period`.|
|`time_point::rep`|Синоним имени вложенного типа `duration::rep`.|

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[time_point](#time_point)|Создает объект `time_point`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[max](#max)|Указывает верхний предел для значения типа `time_point::ref`.|
|[min](#min)|Указывает нижний предел для значения типа `time_point::ref`.|
|[time_since_epoch](#time_since_epoch)|Возвращает сохраненное значение `duration`.|

### <a name="public-operators"></a>Открытые операторы

|name|Описание|
|----------|-----------------|
|[time_point::operator+=](#op_add_eq)|Добавляет указанное значение к хранимой длительности.|
|[time_point::operator-=](#operator-_eq)|Вычитает заданное значение из хранимой длительности.|

## <a name="requirements"></a>Требования

**Заголовок:** \<Chrono >

**Пространство имен:** std::chrono

## <a name="max"></a>  time_point::max

Статический метод, который возвращает верхнюю границу значений типа `time_point::ref`.

```cpp
static constexpr time_point max();
```

### <a name="return-value"></a>Возвращаемое значение

Фактически возвращает `time_point(duration::max())`.

## <a name="min"></a>  time_point::min

Статический метод, который возвращает нижнюю границу для значений типа `time_point::ref`.

```cpp
static constexpr time_point min();
```

### <a name="return-value"></a>Возвращаемое значение

Фактически возвращает `time_point(duration::min())`.

## <a name="op_add_eq"></a>  time_point::operator+=

Добавляет указанное значение к хранимому значению [duration](../standard-library/duration-class.md).

```cpp
time_point& operator+=(const duration& Dur);
```

### <a name="parameters"></a>Параметры

*Ожидаем*\
Объект `duration`.

### <a name="return-value"></a>Возвращаемое значение

Объект `time_point` после добавления.

## <a name="operator-_eq"></a>  time_point::operator-=

Вычитает заданное значение из хранимого значения [duration](../standard-library/duration-class.md).

```cpp
time_point& operator-=(const duration& Dur);
```

### <a name="parameters"></a>Параметры

*Ожидаем*\
Объект `duration`.

### <a name="return-value"></a>Возвращаемое значение

Объект `time_point` после вычитания.

## <a name="time_point"></a> Конструктор time_point::time_point

Создает объект `time_point`.

```cpp
constexpr time_point();

constexpr explicit time_point(const duration& Dur);

template <class Duration2>
constexpr time_point(const time_point<clock, Duration2>& Tp);
```

### <a name="parameters"></a>Параметры

*Ожидаем*\
Объект [duration](../standard-library/duration-class.md).

*Пи*\
Объект `time_point`.

### <a name="remarks"></a>Примечания

Первый конструктор создает объект, хранимое значение `duration` которого равно [duration::zero](../standard-library/duration-class.md#zero).

Второй конструктор конструирует объект, сохраненное значение длительности которого равно *Duration.* Если `is_convertible<Duration2, duration>` не имеет значение true, второй конструктор не участвует в разрешении перегрузки. Дополнительные сведения см. в разделе [<type_traits>](../standard-library/type-traits.md).

Третий конструктор инициализирует свое значение `duration`, используя `Tp.time_since_epoch()`.

## <a name="time_since_epoch"></a>  time_point::time_since_epoch

Извлекает хранимое значение [duration](../standard-library/duration-class.md).

```cpp
constexpr duration time_since_epoch() const;
```

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[\<chrono>](../standard-library/chrono.md)
