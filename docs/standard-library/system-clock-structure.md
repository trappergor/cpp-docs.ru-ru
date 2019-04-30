---
title: Структура system_clock
ms.date: 11/04/2016
f1_keywords:
- chrono/std::chrono::system_clock
- chrono/std::chrono::system_clock::from_time_t
- chrono/std::chrono::system_clock::now
- chrono/std::chrono::system_clock::to_time_t
- chrono/std::chrono::system_clock::is_monotonic Constant
- chrono/std::chrono::system_clock::is_steady Constant
ms.assetid: a97bd46e-267a-4836-9f7d-af1f664e99ae
ms.openlocfilehash: 66710f94d96f069d6d388d6b49c76747c618a0d0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62412154"
---
# <a name="systemclock-structure"></a>Структура system_clock

Представляет *тип clock*, использующий данные системных часов в реальном времени.

## <a name="syntax"></a>Синтаксис

```cpp
struct system_clock;
```

## <a name="remarks"></a>Примечания

*Тип clock* используется для получения текущего времени в формате UTC. Этот тип реализует экземпляр класса [duration](../standard-library/duration-class.md) и шаблон класса [time_point](../standard-library/time-point-class.md), а также определяет статическую функцию-член `now()`, которая возвращает время.

Часы считаются *монотонными*, если значение, возвращаемое при первом вызове `now()`, всегда меньше значения, возвращаемого при последующих вызовах `now()`, или равно ему.

Часы считаются *постоянными*, если они *монотонны* и интервал времени между соседними тактами является постоянной величиной.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|name|Описание|
|----------|-----------------|
|`system_clock::duration`|Синоним для `duration<rep, period>`.|
|`system_clock::period`|Синоним для типа, который используется для представления тактового периода при автономном создании экземпляра `duration`.|
|`system_clock::rep`|Синоним для типа, который используется для представления числа тактов часов при автономном создании экземпляра `duration`.|
|`system_clock::time_point`|Синоним для `time_point<Clock, duration>`, где `Clock` является синонимом для самого типа часов или для другого типа часов, настроенного на ту же эпоху и имеющего тот же вложенный тип `duration`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[from_time_t](#from_time_t)|Статический. Возвращает объект `time_point`, наиболее точно соответствующий указанному времени.|
|[Теперь](#now)|Статический. Возвращает текущее время.|
|[to_time_t](#to_time_t)|Статический. Возвращает объект `time_t`, наиболее точно соответствующий указанному объекту `time_point`.|

### <a name="public-constants"></a>Открытые константы

|name|Описание|
|----------|-----------------|
|[Константа system_clock::is_monotonic](#is_monotonic_constant)|Указывает, являются ли часы монотонными.|
|[Константа system_clock::is_steady](#is_steady_constant)|Указывает, являются ли часы постоянными.|

## <a name="requirements"></a>Требования

**Заголовок:** \<chrono >

**Пространство имен:** std::chrono

## <a name="from_time_t"></a>  system_clock::from_time_t

Статический метод, возвращающий [time_point](../standard-library/time-point-class.md) наиболее точно соответствует времени, представленного *Tm*.

```cpp
static time_point from_time_t(time_t Tm) noexcept;
```

### <a name="parameters"></a>Параметры

*TM*<br/>
Объект [time_t](../c-runtime-library/standard-types.md).

## <a name="is_monotonic_constant"></a>  Константа system_clock::is_monotonic

Статическое значение, указывающее, являются ли часы монотонными.

```cpp
static const bool is_monotonic = false;
```

### <a name="return-value"></a>Возвращаемое значение

В данном случае `system_clock::is_monotonic` всегда возвращает **false**.

### <a name="remarks"></a>Примечания

Часы считаются *монотонными*, если значение, возвращаемое при первом вызове `now()`, всегда меньше значения, возвращаемого при последующих вызовах `now()`, или равно ему.

## <a name="is_steady_constant"></a> Константа system_clock::is_steady

Статическое значение, указывающее, являются ли часы *постоянными*.

```cpp
static const bool is_steady = false;
```

### <a name="return-value"></a>Возвращаемое значение

В данном случае `system_clock::is_steady` всегда возвращает **false**.

### <a name="remarks"></a>Примечания

Часы считаются *постоянными*, если они [монотонны](#is_monotonic_constant) и интервал времени между соседними тактами является постоянной величиной.

## <a name="now"></a>  system_clock::now

Статический метод, который возвращает текущее время.

```cpp
static time_point now() noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Объект [time_point](../standard-library/time-point-class.md), представляющий текущее время.

## <a name="to_time_t"></a>  system_clock::to_time_t

Статический метод, возвращающий [time_t](../c-runtime-library/standard-types.md) наиболее точно соответствует времени, представленного *время*.

```cpp
static time_t to_time_t(const time_point& Time) noexcept;
```

### <a name="parameters"></a>Параметры

*Время*<br/>
Объект [time_point](../standard-library/time-point-class.md).

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<chrono>](../standard-library/chrono.md)<br/>
[Структура steady_clock](../standard-library/steady-clock-struct.md)<br/>
