---
title: Класс unique_lock | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- mutex/std::unique_lock
dev_langs:
- C++
ms.assetid: f4ed8ba9-c8af-446f-8ef0-0b356bad14bd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2b7cd9a949fef63e742d75bc01b199871d4950cc
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38956480"
---
# <a name="uniquelock-class"></a>Класс unique_lock

Представляет шаблон, для которого можно создать экземпляры и объекты, управляющие блокировкой и разблокировкой `mutex`.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Mutex>
class unique_lock;
```

## <a name="remarks"></a>Примечания

В аргументе шаблона `Mutex` должно быть указано имя *типа мьютекс*.

На внутреннем уровне `unique_lock` сохраняет указатель на связанный с ним `mutex` объекта и **bool** , указывающее, владеет ли текущий поток `mutex`.

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание:|
|----------|-----------------|
|`mutex_type`|Синоним для аргумента шаблона `Mutex`.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[unique_lock](#unique_lock)|Создает объект `unique_lock`.|
|[Деструктор ~unique_lock](#dtorunique_lock_destructor)|Освобождает все ресурсы, связанные с объектом `unique_lock`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[lock](#lock)|Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца соответствующего объекта `mutex`.|
|[mutex](#mutex)|Извлекает сохраненный указатель на соответствующий объект `mutex`.|
|[owns_lock](#owns_lock)|Указывает, является ли вызывающий поток владельцем соответствующего объекта `mutex`.|
|[release](#release)|Отменяет связь объекта `unique_lock` с объектом `mutex`.|
|[swap](#swap)|Меняет местами соответствующий `mutex` и статус владения с аналогичными свойствами указанного объекта.|
|[try_lock](#try_lock)|Попытки получить права владельца связанного объекта `mutex` без блокировки.|
|[try_lock_for](#try_lock_for)|Попытки получить права владельца связанного объекта `mutex` без блокировки.|
|[try_lock_until](#try_lock_until)|Попытки получить права владельца связанного объекта `mutex` без блокировки.|
|[unlock](#unlock)|Освобождает права владения для соответствующего объекта `mutex`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[operator bool](#op_bool)|Указывает, является ли вызывающий поток владельцем соответствующего объекта `mutex`.|
|[оператор=](#op_eq)|Копирует сохраненный указатель `mutex` и соответствующее состояние владения из указанного объекта.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`unique_lock`

## <a name="requirements"></a>Требования

**Заголовок:** \<mutex >

**Пространство имен:** std

## <a name="lock"></a>  lock

Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца соответствующего объекта `mutex`.

```cpp
void lock();
```

### <a name="remarks"></a>Примечания

Если сохраненный `mutex` указатель имеет значение NULL, этот метод вызывает исключение [system_error](../standard-library/system-error-class.md) с кодом ошибки `operation_not_permitted`.

Если вызывающий поток уже является владельцем соответствующего объекта `mutex`, этот метод создает исключение `system_error`, содержащее код ошибки `resource_deadlock_would_occur`.

В противном случае этот метод вызывает `lock` в связанном `mutex` и устанавливает флаг владения внутренних потоков **true**.

## <a name="mutex"></a>  mutex

Извлекает сохраненный указатель на соответствующий объект `mutex`.

```cpp
mutex_type *mutex() const noexcept;
```

## <a name="op_bool"></a>  operator bool

Указывает, является ли вызывающий поток владельцем соответствующего мьютекса.

```cpp
explicit operator bool() noexcept
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если поток является владельцем мьютекса; в противном случае **false**.

## <a name="op_eq"></a>  оператор=

Копирует сохраненный указатель `mutex` и соответствующее состояние владения из указанного объекта.

```cpp
unique_lock& operator=(unique_lock&& Other) noexcept;
```

### <a name="parameters"></a>Параметры

*Другое*  
 Объект `unique_lock`.

### <a name="return-value"></a>Возвращаемое значение

`*this`

### <a name="remarks"></a>Примечания

Если вызывающий поток является владельцем ранее назначенного объекта `mutex`, то перед вызовом `unlock` на `mutex` этот метод назначает новые значения.

После копирования этот метод задает *других* в состояние, созданное по умолчанию.

## <a name="owns_lock"></a>  owns_lock

Указывает, является ли вызывающий поток владельцем соответствующего объекта `mutex`.

```cpp
bool owns_lock() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если поток владеет `mutex`; в противном случае **false**.

## <a name="release"></a>  release

Отменяет связь объекта `unique_lock` с объектом `mutex`.

```cpp
mutex_type *release() noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

Предыдущее значение сохраненного указателя `mutex`.

### <a name="remarks"></a>Примечания

Этот метод устанавливает значение сохраненного `mutex` указатель на 0 и устанавливает внутренний `mutex` флаг владения для **false**.

## <a name="swap"></a>  swap

Меняет местами соответствующий `mutex` и статус владения с аналогичными свойствами указанного объекта.

```cpp
void swap(unique_lock& Other) noexcept;
```

### <a name="parameters"></a>Параметры

*Другое*  
 Объект `unique_lock`.

## <a name="try_lock"></a>  try_lock

Попытки получить права владельца связанного объекта `mutex` без блокировки.

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если метод успешно получает права владения `mutex`; в противном случае **false**.

### <a name="remarks"></a>Примечания

Если сохраненный `mutex` указатель имеет значение NULL, этот метод вызывает [system_error](../standard-library/system-error-class.md) с кодом ошибки `operation_not_permitted`.

Если вызывающий поток уже является владельцем объекта `mutex`, этот метод создает исключение `system_error`, содержащее код ошибки `resource_deadlock_would_occur`.

## <a name="try_lock_for"></a>  try_lock_for

Попытки получить права владельца связанного объекта `mutex` без блокировки.

```cpp
template <class Rep, class Period>
bool try_lock_for(
    const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Параметры

*Rel_time*  
 Объект [chrono::duration](../standard-library/duration-class.md), который указывает максимальный интервал времени, в течение которого метод пытается получить права владельца объекта `mutex`.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если метод успешно получает права владения `mutex`; в противном случае **false**.

### <a name="remarks"></a>Примечания

Если сохраненный `mutex` указатель имеет значение NULL, этот метод вызывает [system_error](../standard-library/system-error-class.md) с кодом ошибки `operation_not_permitted`.

Если вызывающий поток уже является владельцем объекта `mutex`, этот метод создает исключение `system_error`, содержащее код ошибки `resource_deadlock_would_occur`.

## <a name="try_lock_until"></a>  try_lock_until

Попытки получить права владельца связанного объекта `mutex` без блокировки.

```cpp
template <class Clock, class Duration>
bool try_lock_until(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```

### <a name="parameters"></a>Параметры

*Abs_time*  
 Момент времени, определяющий порог, после которого метод больше не пытается получить права владельца объекта `mutex`.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если метод успешно получает права владения `mutex`; в противном случае **false**.

### <a name="remarks"></a>Примечания

Если сохраненный `mutex` указатель имеет значение NULL, этот метод вызывает [system_error](../standard-library/system-error-class.md) с кодом ошибки `operation_not_permitted`.

Если вызывающий поток уже является владельцем объекта `mutex`, этот метод создает исключение `system_error`, содержащее код ошибки `resource_deadlock_would_occur`.

## <a name="unique_lock"></a>  Конструктор unique_lock

Создает объект `unique_lock`.

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

*Mtx*  
 Тип объекта мьютекса.

*Rel_time*  
 Объект [chrono::duration](../standard-library/duration-class.md), который указывает максимальный интервал времени, в течение которого метод пытается получить права владельца объекта `mutex`.

*Abs_time*  
 Момент времени, определяющий порог, после которого метод больше не пытается получить права владельца объекта `mutex`.

*Другое*  
 Объект `unique_lock`.

### <a name="remarks"></a>Примечания

Первый конструктор создает объект, у которого значение соответствующего указателя мьютекса равно 0.

Второй конструктор перемещает соответствующее состояние мьютекса из *других*. После перемещения *других* больше не связан с мьютексом.

В оставшихся конструкторах & *Mtx* как сохраненное `mutex` указатель. Состояние владения `mutex` определяется с помощью второго аргумента, если он существует.

|||
|-|-|
|`No argument`|Для получения состояния владения вызывается метод `lock` соответствующего объекта `mutex`.|
|`Adopt`|Предполагается, что состояние владения есть. `Mtx` должен быть заблокирован при вызове конструктора.|
|`Defer`|Предполагается, что вызывающий поток не является владельцем объекта `mutex`. `Mtx` не должен быть заблокирован при вызове конструктора.|
|`Try`|Для получения состояния владения вызывается метод `try_lock` соответствующего объекта `mutex`. Конструктор не выбрасывает никаких исключений.|
|`Rel_time`|Для получения состояния владения вызывается метод `try_lock_for(Rel_time)`.|
|`Abs_time`|Для получения состояния владения вызывается метод `try_lock_until(Abs_time)`.|

## <a name="dtorunique_lock_destructor"></a> Деструктор ~unique_lock

Освобождает все ресурсы, связанные с объектом `unique_lock`.

```cpp
~unique_lock() noexcept;
```

### <a name="remarks"></a>Примечания

Если вызывающий поток является владельцем соответствующего объекта `mutex`, деструктор освобождает права владения, вызывая метод unlock для объекта `mutex`.

## <a name="unlock"></a>  unlock

Освобождает права владения для соответствующего объекта `mutex`.

```cpp
void unlock();
```

### <a name="remarks"></a>Примечания

Если вызывающий поток не является владельцем соответствующего объекта `mutex`, этот метод создает исключение [system_error](../standard-library/system-error-class.md) с кодом ошибки `operation_not_permitted`.

В противном случае этот метод вызывает `unlock` в связанном `mutex` и устанавливает флаг владения внутренних потоков **false**.

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<mutex>](../standard-library/mutex.md)<br/>
