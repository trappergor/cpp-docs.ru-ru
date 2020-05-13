---
title: Класс recursive_timed_mutex
ms.date: 11/04/2016
f1_keywords:
- mutex/std::recursive_timed_mutex
- mutex/std::recursive_timed_mutex::recursive_timed_mutex
- mutex/std::recursive_timed_mutex::lock
- mutex/std::recursive_timed_mutex::try_lock
- mutex/std::recursive_timed_mutex::try_lock_for
- mutex/std::recursive_timed_mutex::try_lock_until
- mutex/std::recursive_timed_mutex::unlock
ms.assetid: 59cc2d5c-ed80-45f3-a0a8-05652a8ead7e
helpviewer_keywords:
- std::recursive_timed_mutex [C++]
- std::recursive_timed_mutex [C++], recursive_timed_mutex
- std::recursive_timed_mutex [C++], lock
- std::recursive_timed_mutex [C++], try_lock
- std::recursive_timed_mutex [C++], try_lock_for
- std::recursive_timed_mutex [C++], try_lock_until
- std::recursive_timed_mutex [C++], unlock
ms.openlocfilehash: 93ce7b99728d1ce89c8124efd6c74aea7ff66d22
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81320136"
---
# <a name="recursive_timed_mutex-class"></a>Класс recursive_timed_mutex

Представляет *тип mutex, приуроченный.* Используйте объекты этого типа для принудительного взаимного исключения с помощью ограниченной по времени блокировки в программе. В отличие от объектов типа [timed_mutex](../standard-library/timed-mutex-class.md), эффект вызова методов блокировки для объектов `recursive_timed_mutex` четко определен.

## <a name="syntax"></a>Синтаксис

```cpp
class recursive_timed_mutex;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[recursive_timed_mutex](#recursive_timed_mutex)|Создает объект `recursive_timed_mutex`, который не заблокирован.|
|[«recursive_timed_mutex деструктор](#dtorrecursive_timed_mutex_destructor)|Освобождает все ресурсы, используемые объектом `recursive_timed_mutex`.|

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

## <a name="lock"></a><a name="lock"></a>Блокировки

Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца объекта `mutex`.

```cpp
void lock();
```

### <a name="remarks"></a>Remarks

Если вызывающий поток уже владеет `mutex`, метод немедленно возвращает значение и предыдущая блокировка остается в силе.

## <a name="recursive_timed_mutex-constructor"></a><a name="recursive_timed_mutex"></a>recursive_timed_mutex конструктор

Создает объект `recursive_timed_mutex`, который не заблокирован.

```cpp
recursive_timed_mutex();
```

## <a name="recursive_timed_mutex-destructor"></a><a name="dtorrecursive_timed_mutex_destructor"></a>  Деструктор ~recursive_timed_mutex

Освобождает все ресурсы, используемые объектом `recursive_timed_mutex`.

```cpp
~recursive_timed_mutex();
```

### <a name="remarks"></a>Remarks

Если при выполнении деструктора объект заблокирован, поведение не определено.

## <a name="try_lock"></a><a name="try_lock"></a>Try_lock

Попытки получить права владельца объекта `mutex` без блокировки.

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

**верно,** если метод успешно получил `mutex` право собственности или `mutex`если вызов поток уже владеет ; в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Если поток вызова уже `mutex`владеет функцией, функция немедленно возвращается **верно,** и предыдущий блокировка остается в силе.

## <a name="try_lock_for"></a><a name="try_lock_for"></a>try_lock_for

Попытки получить права владельца объекта `mutex` без блокировки.

```cpp
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Параметры

*Rel_time*\
Объект [chrono::duration](../standard-library/duration-class.md), который указывает максимальный интервал времени, в течение которого метод пытается получить права владельца объекта `mutex`.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если метод успешно получает `mutex` право собственности на `mutex`или если вызывающая нить уже владеет; в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Если поток вызова уже `mutex`владеет, метод немедленно возвращается **верным,** и предыдущий блокировка остается в силе.

## <a name="try_lock_until"></a><a name="try_lock_until"></a>try_lock_until

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

**верно,** если метод успешно получает `mutex` право собственности на `mutex`или если вызывающая нить уже владеет; в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Если поток вызова уже `mutex`владеет, метод немедленно возвращается **верным,** и предыдущий блокировка остается в силе.

## <a name="unlock"></a><a name="unlock"></a>Разблокировать

Освобождает права владения объектом `mutex`.

```cpp
void unlock();
```

### <a name="remarks"></a>Remarks

Этот метод освобождает владение `mutex` только если он вызван столько раз, сколько [lock](#lock), [try_lock](#try_lock), [try_lock_for](#try_lock_for) и [try_lock_until](#try_lock_until) были успешно вызваны для объекта `recursive_timed_mutex`.

Если вызывающий поток не является владельцем `mutex`, поведение не определено.

## <a name="see-also"></a>См. также раздел

[Справка по файлам заголовка](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
