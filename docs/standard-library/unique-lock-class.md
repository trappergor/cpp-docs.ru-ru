---
title: Класс unique_lock
ms.date: 11/04/2016
f1_keywords:
- mutex/std::unique_lock
ms.assetid: f4ed8ba9-c8af-446f-8ef0-0b356bad14bd
ms.openlocfilehash: 59201fbaba6f2e8ae0ed5f53925b287b4d33aab3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367261"
---
# <a name="unique_lock-class"></a>Класс unique_lock

Представляет шаблон, для которого можно создать экземпляры и объекты, управляющие блокировкой и разблокировкой `mutex`.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Mutex>
class unique_lock;
```

## <a name="remarks"></a>Remarks

В аргументе шаблона `Mutex` должно быть указано имя *типа мьютекс*.

`unique_lock` Внутренне хранит указатель на связанный `mutex` объект и **bool,** который указывает, `mutex`является ли текущий поток владеет .

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`mutex_type`|Синоним для аргумента шаблона `Mutex`.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[unique_lock](#unique_lock)|Формирует объект `unique_lock`.|
|[«unique_lock деструктор](#dtorunique_lock_destructor)|Освобождает все ресурсы, связанные с объектом `unique_lock`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[lock](#lock)|Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца соответствующего объекта `mutex`.|
|[мьютекс](#mutex)|Извлекает сохраненный указатель на соответствующий объект `mutex`.|
|[owns_lock](#owns_lock)|Указывает, является ли вызывающий поток владельцем соответствующего объекта `mutex`.|
|[Выпуска](#release)|Отменяет связь объекта `unique_lock` с объектом `mutex`.|
|[Своп](#swap)|Меняет местами соответствующий `mutex` и статус владения с аналогичными свойствами указанного объекта.|
|[try_lock](#try_lock)|Попытки получить права владельца связанного объекта `mutex` без блокировки.|
|[try_lock_for](#try_lock_for)|Попытки получить права владельца связанного объекта `mutex` без блокировки.|
|[try_lock_until](#try_lock_until)|Попытки получить права владельца связанного объекта `mutex` без блокировки.|
|[Разблокировать](#unlock)|Освобождает права владения для соответствующего объекта `mutex`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[оператор bool](#op_bool)|Указывает, является ли вызывающий поток владельцем соответствующего объекта `mutex`.|
|[оператора](#op_eq)|Копирует сохраненный указатель `mutex` и соответствующее состояние владения из указанного объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

*unique_lock*

## <a name="requirements"></a>Требования

**Заголовок:** \<mutex>

**Пространство имен:** std

## <a name="lock"></a><a name="lock"></a>Блокировки

Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца соответствующего объекта `mutex`.

```cpp
void lock();
```

### <a name="remarks"></a>Remarks

Если сохраненная `mutex` указатель NULL, этот метод бросает [system_error,](../standard-library/system-error-class.md) `operation_not_permitted`который имеет код ошибки.

Если вызывающий поток уже является владельцем соответствующего объекта `mutex`, этот метод создает исключение `system_error`, содержащее код ошибки `resource_deadlock_would_occur`.

В противном `lock` случае этот `mutex` метод вызывает связанный и устанавливает внутренний флаг собственности потока к **истине.**

## <a name="mutex"></a><a name="mutex"></a>Мьютекс

Извлекает сохраненный указатель на соответствующий объект `mutex`.

```cpp
mutex_type *mutex() const noexcept;
```

## <a name="operator-bool"></a><a name="op_bool"></a>оператор bool

Указывает, является ли вызывающий поток владельцем соответствующего мьютекса.

```cpp
explicit operator bool() noexcept
```

### <a name="return-value"></a>Возвращаемое значение

**верно,** если поток владеет mutex; в противном случае **ложные**.

## <a name="operator"></a><a name="op_eq"></a>оператора

Копирует сохраненный указатель `mutex` и соответствующее состояние владения из указанного объекта.

```cpp
unique_lock& operator=(unique_lock&& Other) noexcept;
```

### <a name="parameters"></a>Параметры

*Других*\
Объект `unique_lock` .

### <a name="return-value"></a>Возвращаемое значение

`*this`

### <a name="remarks"></a>Remarks

Если вызывающий поток является владельцем ранее назначенного объекта `mutex`, то перед вызовом `unlock` на `mutex` этот метод назначает новые значения.

После копирования этот метод устанавливает *другое* к состоянию, построенному по умолчанию.

## <a name="owns_lock"></a><a name="owns_lock"></a>owns_lock

Указывает, является ли вызывающий поток владельцем соответствующего объекта `mutex`.

```cpp
bool owns_lock() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

**верно,** если нить владеет `mutex`; в противном случае, **ложные**.

## <a name="release"></a><a name="release"></a>Выпуска

Отменяет связь объекта `unique_lock` с объектом `mutex`.

```cpp
mutex_type *release() noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Предыдущее значение сохраненного указателя `mutex`.

### <a name="remarks"></a>Remarks

Этот метод устанавливает значение `mutex` хранимого указателя `mutex` до 0 и устанавливает внутренний флаг собственности на **ложный.**

## <a name="swap"></a><a name="swap"></a>Своп

Меняет местами соответствующий `mutex` и статус владения с аналогичными свойствами указанного объекта.

```cpp
void swap(unique_lock& Other) noexcept;
```

### <a name="parameters"></a>Параметры

*Других*\
Объект `unique_lock` .

## <a name="try_lock"></a><a name="try_lock"></a>Try_lock

Попытки получить права владельца связанного объекта `mutex` без блокировки.

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

**верно,** если метод успешно получает `mutex`право собственности на ; в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Если сохраненная `mutex` указатель NULL, метод бросает [system_error,](../standard-library/system-error-class.md) который `operation_not_permitted`имеет код ошибки.

Если вызывающий поток уже является владельцем объекта `mutex`, этот метод создает исключение `system_error`, содержащее код ошибки `resource_deadlock_would_occur`.

## <a name="try_lock_for"></a><a name="try_lock_for"></a>try_lock_for

Попытки получить права владельца связанного объекта `mutex` без блокировки.

```cpp
template <class Rep, class Period>
bool try_lock_for(
    const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Параметры

*Rel_time*\
Объект [chrono::duration](../standard-library/duration-class.md), который указывает максимальный интервал времени, в течение которого метод пытается получить права владельца объекта `mutex`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если метод успешно получает `mutex`право собственности на ; в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Если сохраненная `mutex` указатель NULL, метод бросает [system_error,](../standard-library/system-error-class.md) который `operation_not_permitted`имеет код ошибки.

Если вызывающий поток уже является владельцем объекта `mutex`, этот метод создает исключение `system_error`, содержащее код ошибки `resource_deadlock_would_occur`.

## <a name="try_lock_until"></a><a name="try_lock_until"></a>try_lock_until

Попытки получить права владельца связанного объекта `mutex` без блокировки.

```cpp
template <class Clock, class Duration>
bool try_lock_until(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```

### <a name="parameters"></a>Параметры

*Abs_time*\
Момент времени, определяющий порог, после которого метод больше не пытается получить права владельца объекта `mutex`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если метод успешно получает `mutex`право собственности на ; в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Если сохраненная `mutex` указатель NULL, метод бросает [system_error,](../standard-library/system-error-class.md) который `operation_not_permitted`имеет код ошибки.

Если вызывающий поток уже является владельцем объекта `mutex`, этот метод создает исключение `system_error`, содержащее код ошибки `resource_deadlock_would_occur`.

## <a name="unique_lock-constructor"></a><a name="unique_lock"></a>unique_lock конструктор

Формирует объект `unique_lock`.

```cpp
unique_lock() noexcept;
unique_lock(unique_lock&& Other) noexcept;
explicit unique_lock(mutex_type& Mtx);

unique_lock(mutex_type& Mtx, adopt_lock_t Adopt);

unique_lock(mutex_type& Mtx, defer_lock_t Defer) noexcept;
unique_lock(mutex_type& Mtx, try_to_lock_t Try);

template <class Rep, class Period>
unique_lock(mutex_type& Mtx,
    const chrono::duration<Rep, Period>
Rel_time);

template <class Clock, class Duration>
unique_lock(mutex_type& Mtx,
    const chrono::time_point<Clock, Duration>
Abs_time);

unique_lock(mutex_type& Mtx,
    const xtime* Abs_time) noexcept;
```

### <a name="parameters"></a>Параметры

*Mtx*\
Тип объекта мьютекса.

*Rel_time*\
Объект [chrono::duration](../standard-library/duration-class.md), который указывает максимальный интервал времени, в течение которого метод пытается получить права владельца объекта `mutex`.

*Abs_time*\
Момент времени, определяющий порог, после которого метод больше не пытается получить права владельца объекта `mutex`.

*Других*\
Объект `unique_lock` .

### <a name="remarks"></a>Remarks

Первый конструктор создает объект, у которого значение соответствующего указателя мьютекса равно 0.

Второй конструктор перемещает связанный статус mutex из *другого.* После *перемещения, Другие* больше не связаны с mutex.

Остальные конструкторы хранят & *Mtx* `mutex` в качестве хранимой указки. Состояние владения `mutex` определяется с помощью второго аргумента, если он существует.

|||
|-|-|
|`No argument`|Для получения состояния владения вызывается метод `lock` соответствующего объекта `mutex`.|
|`Adopt`|Предполагается, что состояние владения есть. `Mtx` должен быть заблокирован при вызове конструктора.|
|`Defer`|Предполагается, что вызывающий поток не является владельцем объекта `mutex`. `Mtx` не должен быть заблокирован при вызове конструктора.|
|`Try`|Для получения состояния владения вызывается метод `try_lock` соответствующего объекта `mutex`. Конструктор не выбрасывает никаких исключений.|
|`Rel_time`|Для получения состояния владения вызывается метод `try_lock_for(Rel_time)`.|
|`Abs_time`|Для получения состояния владения вызывается метод `try_lock_until(Abs_time)`.|

## <a name="unique_lock-destructor"></a><a name="dtorunique_lock_destructor"></a> Деструктор ~unique_lock

Освобождает все ресурсы, связанные с объектом `unique_lock`.

```cpp
~unique_lock() noexcept;
```

### <a name="remarks"></a>Remarks

Если вызывающий поток является владельцем соответствующего объекта `mutex`, деструктор освобождает права владения, вызывая метод unlock для объекта `mutex`.

## <a name="unlock"></a><a name="unlock"></a>Разблокировать

Освобождает права владения для соответствующего объекта `mutex`.

```cpp
void unlock();
```

### <a name="remarks"></a>Remarks

Если вызывающий поток не является владельцем соответствующего объекта `mutex`, этот метод создает исключение [system_error](../standard-library/system-error-class.md) с кодом ошибки `operation_not_permitted`.

В противном `unlock` случае этот `mutex` метод вызывает связанный и устанавливает внутренний флаг собственности потока на **ложный.**

## <a name="see-also"></a>См. также раздел

[Справка по файлам заголовка](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
