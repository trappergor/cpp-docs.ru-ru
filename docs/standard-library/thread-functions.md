---
title: Функции &lt;thread&gt; | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.topic: reference
f1_keywords:
- thread/std::get_id
- thread/std::sleep_for
- thread/std::sleep_until
- thread/std::swap
- thread/std::yield
ms.assetid: bb1aa1ef-fe3f-4e2c-8b6e-e22dbf2f5a19
helpviewer_keywords:
- std::get_id [C++]
- std::sleep_for [C++]
- std::sleep_until [C++]
- std::swap [C++]
- std::yield [C++]
ms.openlocfilehash: 25c03be7ffb504f2bec47677aec70360d0f8b38f
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45704265"
---
# <a name="ltthreadgt-functions"></a>Функции &lt;thread&gt;

||||
|-|-|-|
|[get_id](#get_id)|[sleep_for](#sleep_for)|[sleep_until](#sleep_until)|
|[swap](#swap)|[yield](#yield)|

## <a name="get_id"></a>  get_id

Уникально идентифицирует текущий поток выполнения.

```cpp
thread::id this_thread::get_id() noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Объект типа [thread::id](../standard-library/thread-class.md), который уникально идентифицирует текущий поток выполнения.

## <a name="sleep_for"></a>  sleep_for

Блокирует вызывающий поток.

```cpp
template <class Rep,
class Period>
inline void sleep_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Параметры

*Rel_time*<br/>
Объект [duration](../standard-library/duration-class.md), задающий интервал времени.

### <a name="remarks"></a>Примечания

Функция блокирует вызывающий поток для по крайней мере времени, который задается параметром *Rel_time*. Эта функция не вызывает исключений.

## <a name="sleep_until"></a>  sleep_until

Блокирует вызывающий поток по крайней мере до указанного времени.

```cpp
template <class Clock, class Duration>
void sleep_until(const chrono::time_point<Clock, Duration>& Abs_time);

void sleep_until(const xtime *Abs_time);
```

### <a name="parameters"></a>Параметры

*Abs_time*<br/>
Представляет момент времени.

### <a name="remarks"></a>Примечания

Эта функция не вызывает исключений.

## <a name="swap"></a>  swap

Меняет местами состояния двух **поток** объектов.

```cpp
void swap(thread& Left, thread& Right) noexcept;
```

### <a name="parameters"></a>Параметры

*Слева*<br/>
Слева **поток** объекта.

*Справа*<br/>
Справа **поток** объекта.

### <a name="remarks"></a>Примечания

Функция вызывает `Left.swap(Right)`.

## <a name="yield"></a>  yield

Сигнализирует операционной системе, что необходимо запустить другие потоки, даже если в обычной ситуации текущий поток продолжал бы выполняться.

```cpp
inline void yield() noexcept;
```

## <a name="see-also"></a>См. также

[\<thread>](../standard-library/thread.md)<br/>
