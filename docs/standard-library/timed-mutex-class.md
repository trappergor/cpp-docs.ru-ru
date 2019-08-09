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
ms.openlocfilehash: 6b9785dc41791be63d585d18802953eade370b2a
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68459925"
---
# <a name="timedmutex-class"></a>Класс timed_mutex

Представляет *тип мьютекса с ограничением по времени*. Используйте объекты этого типа для принудительного взаимного исключения с помощью ограниченной по времени блокировки в программе.

## <a name="syntax"></a>Синтаксис

```cpp
class timed_mutex;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[timed_mutex](#timed_mutex)|Создает объект `timed_mutex`, который не заблокирован.|
|[Деструктор timed_mutex::~timed_mutex](#dtortimed_mutex_destructor)|Освобождает все ресурсы, используемые объектом `timed_mutex`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[lock](#lock)|Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца объекта `mutex`.|
|[try_lock](#try_lock)|Попытки получить права владельца объекта `mutex` без блокировки.|
|[try_lock_for](#try_lock_for)|Пытается получить права владельца `mutex` на заданный интервал времени.|
|[try_lock_until](#try_lock_until)|Пытается получить права владельца `mutex` до заданного времени.|
|[unlock](#unlock)|Освобождает права владения объектом `mutex`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<> мьютекса

**Пространство имен:** std

## <a name="lock"></a>  timed_mutex::lock

Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца объекта `mutex`.

```cpp
void lock();
```

### <a name="remarks"></a>Примечания

Если вызывающий поток уже является владельцем `mutex`, поведение не определено.

## <a name="timed_mutex"></a>  Конструктор timed_mutex::timed_mutex

Создает объект `timed_mutex`, который не заблокирован.

```cpp
timed_mutex();
```

## <a name="dtortimed_mutex_destructor"></a>  Деструктор timed_mutex::~timed_mutex

Освобождает все ресурсы, используемые объектом `mutex`.

```cpp
~timed_mutex();
```

### <a name="remarks"></a>Примечания

Если при выполнении деструктора объект заблокирован, поведение не определено.

## <a name="try_lock"></a>  timed_mutex::try_lock

Попытки получить права владельца объекта `mutex` без блокировки.

```cpp
bool try_lock();
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если метод успешно получает владение `mutex`; в противном случае — **значение false**.

### <a name="remarks"></a>Примечания

Если вызывающий поток уже является владельцем `mutex`, поведение не определено.

## <a name="try_lock_for"></a>  timed_mutex::try_lock_for

Попытки получить права владельца объекта `mutex` без блокировки.

```cpp
template <class Rep, class Period>
bool try_lock_for(const chrono::duration<Rep, Period>& Rel_time);
```

### <a name="parameters"></a>Параметры

*Rel_time*\
Объект [chrono::duration](../standard-library/duration-class.md), который указывает максимальный интервал времени, в течение которого метод пытается получить права владельца объекта `mutex`.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если метод успешно получает владение `mutex`; в противном случае — **значение false**.

### <a name="remarks"></a>Примечания

Если вызывающий поток уже является владельцем `mutex`, поведение не определено.

## <a name="try_lock_until"></a>  timed_mutex::try_lock_until

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

**значение true** , если метод успешно получает владение `mutex`; в противном случае — **значение false**.

### <a name="remarks"></a>Примечания

Если вызывающий поток уже является владельцем `mutex`, поведение не определено.

## <a name="unlock"></a>  timed_mutex::unlock

Освобождает права владения объектом `mutex`.

```cpp
void unlock();
```

### <a name="remarks"></a>Примечания

Если вызывающий поток не является владельцем `mutex`, поведение не определено.

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
