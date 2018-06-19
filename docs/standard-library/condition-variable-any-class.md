---
title: Класс condition_variable_any | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- condition_variable/std::condition_variable_any
- condition_variable/std::condition_variable_any::condition_variable_any
- condition_variable/std::condition_variable_any::notify_all
- condition_variable/std::condition_variable_any::notify_one
- condition_variable/std::condition_variable_any::wait
- condition_variable/std::condition_variable_any::wait_for
- condition_variable/std::condition_variable_any::wait_until
dev_langs:
- C++
ms.assetid: d8afe5db-1561-4ec2-8e85-21ea03ee4321
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::condition_variable_any
- std::condition_variable_any::condition_variable_any
- std::condition_variable_any::notify_all
- std::condition_variable_any::notify_one
- std::condition_variable_any::wait
- std::condition_variable_any::wait_for
- std::condition_variable_any::wait_until
ms.workload:
- cplusplus
ms.openlocfilehash: f0fe38031dc215f537d82fe6e06f68acf6db8e0f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33847134"
---
# <a name="conditionvariableany-class"></a>Класс condition_variable_any

Класс `condition_variable_any` используется для ожидания события, которое имеет любой тип `mutex`.

## <a name="syntax"></a>Синтаксис

```cpp
class condition_variable_any;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[condition_variable_any](#condition_variable_any)|Создает объект `condition_variable_any`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[notify_all](#notify_all)|Разблокирует все потоки, которые ожидают объект `condition_variable_any`.|
|[notify_one](#notify_one)|Разблокирует один из потоков, которые ожидают объект `condition_variable_any`.|
|[wait](#wait)|Блокирует поток.|
|[wait_for](#wait_for)|Блокирует поток и задает интервал времени, после которого поток разблокируется.|
|[wait_until](#wait_until)|Блокирует поток и задает максимальный момент времени, в который поток разблокируется.|

## <a name="requirements"></a>Требования

**Заголовок:** \<condition_variable >

**Пространство имен:** std

## <a name="condition_variable_any"></a> Конструктор condition_variable_any::condition_variable_any

Создает объект `condition_variable_any`.

```cpp
condition_variable_any();
```

### <a name="remarks"></a>Примечания

При недостатке памяти этот конструктор вызывает объект [system_error](../standard-library/system-error-class.md), имеющий код ошибки `not_enough_memory`. Если объект не может быть создан из-за недоступности некоторых других ресурсов, конструктор создает объект `system_error`, имеющий код ошибки `resource_unavailable_try_again`.

## <a name="notify_all"></a>  condition_variable_any::notify_all

Разблокирует все потоки, которые ожидают объект `condition_variable_any`.

```cpp
void notify_all() noexcept;
```

## <a name="notify_one"></a>  condition_variable_any::notify_one

Разблокирует один из потоков, которые ожидают объект `condition_variable_any`.

```cpp
void notify_one() noexcept;
```

## <a name="wait"></a>  condition_variable_any::wait

Блокирует поток.

```cpp
template <class Lock>
void wait(Lock& Lck);

template <class Lock, class Predicate>
void wait(Lock& Lck, Predicate Pred);
```

### <a name="parameters"></a>Параметры

`Lck` Объект `mutex` объект любого типа.

`Pred` Любое выражение, возвращающее `true` или `false`.

### <a name="remarks"></a>Примечания

Первый метод блокируется до оповещения объекта `condition_variable_any` путем вызова [notify_one](../standard-library/condition-variable-class.md#notify_one) или [notify_all](../standard-library/condition-variable-class.md#notify_all). Он может также ложно активироваться.

Второй метод фактически выполняет следующий код.

```cpp
while (!Pred())
    wait(Lck);
```

## <a name="wait_for"></a>  condition_variable_any::wait_for

Блокирует поток и задает интервал времени, после которого поток разблокируется.

```cpp
template <class Lock, class Rep, class Period>
bool wait_for(Lock& Lck, const chrono::duration<Rep, Period>& Rel_time);

template <class Lock, class Rep, class Period, class Predicate>
bool wait_for(Lock& Lck, const chrono::duration<Rep, Period>& Rel_time, Predicate Pred);
```

### <a name="parameters"></a>Параметры

`Lck` Объект `mutex` объект любого типа.

`Rel_time` Объект `chrono::duration` , указывающий количество времени до истечения которого поток выходит из спящего режима.

`Pred` Любое выражение, возвращающее `true` или `false`.

### <a name="return-value"></a>Возвращаемое значение

Первый метод возвращает `cv_status::timeout`, если ожидание прекращается, когда прошло `Rel_time`. В противном случае метод возвращает значение `cv_status::no_timeout`.

Второй метод возвращает значение `Pred`.

### <a name="remarks"></a>Примечания

Первый метод блокируется до оповещения объекта `condition_variable_any` путем вызова [notify_one](../standard-library/condition-variable-class.md#notify_one) или [notify_all](../standard-library/condition-variable-class.md#notify_all), или до завершения временного интервала `Rel_time`. Он может также ложно активироваться.

Второй метод фактически выполняет следующий код.

```cpp
while(!Pred())
    if(wait_for(Lck, Rel_time) == cv_status::timeout)
    return Pred();

return true;
```

## <a name="wait_until"></a>  condition_variable_any::wait_until

Блокирует поток и задает максимальный момент времени, в который поток разблокируется.

```cpp
template <class Lock, class Clock, class Duration>
void wait_until(Lock& Lck, const chrono::time_point<Clock, Duration>& Abs_time);

template <class Lock, class Clock, class Duration, class Predicate>
void wait_until(
    Lock& Lck,
    const chrono::time_point<Clock, Duration>& Abs_time,
    Predicate Pred);

template <class Lock>
void wait_until(Lock Lck, const xtime* Abs_time);

template <class Lock, class Predicate>
void wait_until(
    Lock Lck,
    const xtime* Abs_time,
    Predicate Pred);
```

### <a name="parameters"></a>Параметры

`Lck` Объект взаимного исключения.

`Abs_time` Объект [chrono::time_point](../standard-library/time-point-class.md) объекта.

`Pred` Любое выражение, возвращающее `true` или `false`.

### <a name="return-value"></a>Возвращаемое значение

Методы, возвращающие тип `cv_status`, возвращают `cv_status::timeout`, если ожидание прекращается, когда истекает `Abs_time`. В противном случае эти методы возвращают `cv_status::no_timeout`.

Методы, возвращающие `bool` возвращают значение `Pred`.

### <a name="remarks"></a>Примечания

Первый метод блокируется до оповещения объекта `condition_variable` путем вызова [notify_one](../standard-library/condition-variable-class.md#notify_one) или [notify_all](../standard-library/condition-variable-class.md#notify_all)`Abs_time`. Он может также ложно активироваться.

Второй метод фактически выполняет следующий код.

```cpp
while(!Pred())
    if(wait_until(Lck, Abs_time) == cv_status::timeout)
    return Pred();

return true;
```

Третий и четвертый методы используют указатель на объект типа `xtime` для замены объекта `chrono::time_point`. Объект `xtime` задает максимальное время ожидания сигнала.

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[<condition_variable>](../standard-library/condition-variable.md)<br/>
