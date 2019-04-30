---
title: Функции &lt;chrono&gt;
ms.date: 11/04/2016
f1_keywords:
- chrono/std::duration_cast
- chrono/std::time_point_cast
ms.assetid: d6800e15-77a1-4df3-900e-d8b2fee190c7
ms.openlocfilehash: 5aadf776cc25e22a40ed75f854481dff63cce4bb
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62371669"
---
# <a name="ltchronogt-functions"></a>Функции &lt;chrono&gt;

||||
|-|-|-|
|[duration_cast](#duration_cast)|[time_point_cast](#time_point_cast)|

## <a name="duration_cast"></a>  duration_cast

Приводит объект `duration` к указанному типу.

```cpp
template <class To, class Rep, class Period>
constexpr To duration_cast(const duration<Rep, Period>& Dur);
```

### <a name="return-value"></a>Возвращаемое значение

Объект `duration` типа `To`, представляющий интервал времени `Dur`, который усекается, если должен соответствовать целевому типу.

### <a name="remarks"></a>Примечания

Если `To` является экземпляром `duration`, эта функция не участвует в разрешении перегрузки.

## <a name="time_point_cast"></a>  time_point_cast

Приводит объект [time_point](../standard-library/time-point-class.md) к указанному типу.

```cpp
template <class To, class Clock, class Duration>
time_point<Clock, To> time_point_cast(const time_point<Clock, Duration>& Tp);
```

### <a name="return-value"></a>Возвращаемое значение

Объект `time_point`, который имеет длительность типа `To`.

### <a name="remarks"></a>Примечания

Если `To` не является экземпляром [duration](../standard-library/duration-class.md), эта функция не участвует в разрешении перегрузки.

## <a name="see-also"></a>См. также

[\<chrono>](../standard-library/chrono.md)<br/>
