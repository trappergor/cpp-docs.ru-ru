---
title: Класс timed_mutex
ms.date: 11/04/2016
f1_keywords:
- mutex/std::timed_mutex
- mutex/std::timed_mutex::timed_mutex
- mutex/std::timed_mutex::lock
- mutex/std::timed_mutex::try_lock
- mutex/std::timed_mutex::try_lock_for
- mutex/std::timed_mutex::try_lock_until
- mutex/std::timed_mutex::unlock
ms.assetid: cd198081-6f38-447a-9dba-e06dfbfafe59
helpviewer_keywords:
- std::timed_mutex [C++]
- std::timed_mutex [C++], timed_mutex
- std::timed_mutex [C++], lock
- std::timed_mutex [C++], try_lock
- std::timed_mutex [C++], try_lock_for
- std::timed_mutex [C++], try_lock_until
- std::timed_mutex [C++], unlock
ms.openlocfilehash: 6c9840d9b8c00d4b03e6ea329c7707a0edff9512
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368020"
---
# <a name="timed_mutex-class"></a>Класс timed_mutex

Представляет *тип mutex, приуроченный.* Используйте объекты этого типа для принудительного взаимного исключения с помощью ограниченной по времени блокировки в программе.

## <a name="syntax"></a>Синтаксис

```cpp
class timed_mutex;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[timed_mutex](#timed_mutex)|Создает объект `timed_mutex`, который не заблокирован.|
|[timed_mutex::timed_mutex деструктор](#dtortimed_mutex_destructor)|Освобождает все ресурсы, используемые объектом `timed_mutex`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[lock](#lock)|Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца объекта `mutex`.|
|[try_lock](#try_lock)|Попытки получить права владельца объекта `mutex` без блокировки.|
|[try_lock_for](#try_lock_for)|Пытается получить права владельца `mutex` на заданный интервал времени.|
|[try_lock_until](#try_lock_until)|Пытается получить права владельца `mutex` до заданного времени.|
|[Разблокировать](#unlock)|Освобождает права владения объектом `mutex`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<mutex>

**Пространство имен:** std

## <a name="timed_mutexlock"></a><a name="lock"></a>timed_mutex::lock

Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца объекта `mutex`.

```cpp
void lock();
```

### <a name="remarks"></a>Remarks

Если вызывающий поток уже является владельцем `mutex`, поведение не определено.

## <a name="timed_mutextimed_mutex-constructor"></a><a name="timed_mutex"></a>timed_mutex::timed_mutex конструктор

Создает объект `timed_mutex`, который не заблокирован.

```cpp
timed_mutex();
```

## <a name="timed_mutextimed_mutex-destructor"></a><a name="dtortimed_mutex_destructor"></a>timed_mutex::timed_mutex деструктор

Освобождает все ресурсы, используемые объектом `mutex`.

```cpp
~timed_mutex();
```

### <a name="remarks"></a>Remarks

Если при выполнении деструктора объект заблокирован, поведение не определено.

## <a name="timed_mutextry_lock"></a><a name="try_lock"></a>timed_mutex:::try_lock

Попытки получить права владельца объекта `mutex` без блокировки.

```cpp
bool try_lock();
```

### <a name="return-value"></a>Возвращаемое значение

**верно,** если метод успешно получает `mutex`право собственности на ; в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Если вызывающий поток уже является владельцем `mutex`, поведение не определено.

## <a name="timed_mutextry_lock_for"></a><a name="try_lock_for"></a>timed_mutex::try_lock_for

Попытки получить права владельца объекта `mutex` без блокировки.

```cpp
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Параметры

*Rel_time*\
Объект [chrono::duration](../standard-library/duration-class.md), который указывает максимальный интервал времени, в течение которого метод пытается получить права владельца объекта `mutex`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если метод успешно получает `mutex`право собственности на ; в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Если вызывающий поток уже является владельцем `mutex`, поведение не определено.

## <a name="timed_mutextry_lock_until"></a><a name="try_lock_until"></a>timed_mutex::try_lock_until

Попытки получить права владельца объекта `mutex` без блокировки.

```cpp
template <class Clock, class Duration>
bool try_lock_for(const chrono::time_point<Clock, Duration>& Abs_time);

bool try_lock_until(const xtime* Abs_time);
```

### <a name="parameters"></a>Параметры

*Abs_time*\
Момент времени, определяющий порог, после которого метод больше не пытается получить права владельца объекта `mutex`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если метод успешно получает `mutex`право собственности на ; в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Если вызывающий поток уже является владельцем `mutex`, поведение не определено.

## <a name="timed_mutexunlock"></a><a name="unlock"></a>timed_mutex::разблокировка

Освобождает права владения объектом `mutex`.

```cpp
void unlock();
```

### <a name="remarks"></a>Remarks

Если вызывающий поток не является владельцем `mutex`, поведение не определено.

## <a name="see-also"></a>См. также раздел

[Справка по файлам заголовка](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
