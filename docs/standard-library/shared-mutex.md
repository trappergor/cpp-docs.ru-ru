---
title: '&lt;shared_mutex&gt; | Документы Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- <shared_mutex>
- shared_mutex/std::swap
- shared_mutex/std::shared_lock
- shared_mutex/std::shared_lock::shared_lock
- shared_mutex/std::shared_lock::operator=
- shared_mutex/std::shared_lock::operator =
- shared_mutex/std::shared_lock::lock
- shared_mutex/std::shared_lock::try_lock
- shared_mutex/std::shared_lock::try_lock_for
- shared_mutex/std::shared_lock::try_lock_until
- shared_mutex/std::shared_lock::unlock
- shared_mutex/std::shared_lock::swap
- shared_mutex/std::shared_lock::release
- shared_mutex/std::shared_lock::owns_lock
- shared_mutex/std::shared_lock::operator bool
- shared_mutex/std::shared_lock::mutex
- shared_mutex/std::shared_mutex
- shared_mutex/std::shared_mutex::native_handle_type
- shared_mutex/std::shared_mutex::shared_mutex
- shared_mutex/std::shared_mutex::operator=
- shared_mutex/std::shared_mutex::operator =
- shared_mutex/std::shared_mutex::lock
- shared_mutex/std::shared_mutex::try_lock
- shared_mutex/std::shared_mutex::unlock
- shared_mutex/std::shared_mutex::lock_shared
- shared_mutex/std::shared_mutex::try_lock_shared
- shared_mutex/std::shared_mutex::unlock_shared
- shared_mutex/std::shared_mutex::native_handle
- shared_mutex/std::shared_timed_mutex
- shared_mutex/std::shared_timed_mutex::shared_timed_mutex
- shared_mutex/std::shared_timed_mutex::operator=
- shared_mutex/std::shared_timed_mutex::operator =
- shared_mutex/std::shared_timed_mutex::lock
- shared_mutex/std::shared_timed_mutex::try_lock
- shared_mutex/std::shared_timed_mutex::try_lock_for
- shared_mutex/std::shared_timed_mutex::try_lock_until
- shared_mutex/std::shared_timed_mutex::unlock
- shared_mutex/std::shared_timed_mutex::lock_shared
- shared_mutex/std::shared_timed_mutex::try_lock_shared
- shared_mutex/std::shared_timed_mutex::try_lock_shared_for
- shared_mutex/std::shared_timed_mutex::try_lock_shared_until
- shared_mutex/std::shared_timed_mutex::unlock_shared
dev_langs:
- C++
ms.assetid: 0b37a97d-ee5d-4050-b29f-09db9f76beb3
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4a9cd6c4533b3b59fdb3c5cab17ffaba071fb08
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="ltsharedmutex"></a>&lt;shared_mutex >

&lt;Shared_mutex > заголовок предоставляет примитивы синхронизации, для защиты общих данных, которые доступны из нескольких потоков. Помимо монопольного доступа, предоставляемого классами mutex, классы shared mutex также предоставляют возможность совместного владения из нескольких потоков для неисключительного доступа. Общие мьютексы можно использовать для управления ресурсами, которые могут считываться несколькими потоками без возникновения состязания, однако должны записываться строго одним потоком.

Заголовок &lt;shared_mutex > определяет классы `shared_mutex` и `shared_timed_mutex`, класс шаблона `shared_lock`и функцию шаблона `swap` для общих поддержки мьютекса.

|Классы|Описание|
|-------------|-----------------|
|[Класс shared_mutex](../standard-library/shared-mutex.md#class_shared_mutex)|Тип общего мьютекса, который может быть заблокирован одним агентом или совместно использоваться несколькими агентами с неисключительным доступом.|
|[Класс shared_timed_mutex](../standard-library/shared-mutex.md#class_shared_timed_mutex)|Тип общего мьютекса с ограничением по времени, который может быть заблокирован одним агентом или совместно использоваться несколькими агентами с неисключительным доступом.|
|[Класс shared_lock](../standard-library/shared-mutex.md#class_shared_lock)|Класс шаблонов, создающий программу-оболочку для общего мьютекса, чтобы обеспечить поддержку операций блокировки с ограничением по времени и совместное использование несколькими агентами с неисключительными правами.|

|Функции|Описание|
|---------------|-----------------|
|[swap](../standard-library/shared-mutex.md#function_swap)|Меняет местами содержимое общих объектов мьютекса, на которые ссылаются параметры функции.|

## <a name="syntax"></a>Синтаксис

```cpp
namespace std {
    class shared_mutex;
    class shared_timed_mutex;
    template <class Mutex>
class shared_lock;
    template <class Mutex>
void swap(shared_lock<Mutex>& x, shared_lock<Mutex>& y) noexcept;
}
```

## <a name="remarks"></a>Примечания

Экземпляр класса `shared_mutex` — это *тип shared mutex*, то есть тип, контролирующий совместное владение мьютексом внутри области. Тип общего мьютекса отвечает всем требованиям типа мьютекса и членов для поддержки общего неисключительного владения.

Тип общего мьютекса поддерживает дополнительные методы `lock_shared`, `unlock_shared` и `try_lock_shared`:

- Метод `lock_shared` блокирует вызывающий поток до тех пор, пока этот поток не получит права совместного владения мьютексом.

- Метод `unlock_shared` выпускает права совместного владения мьютексом, который содержится в вызывающем потоке.

- Метод `try_lock_shared` пытается получить совместное владение мьютексом без блокировки. Его возвращаемое значение можно преобразовать в `bool` и оно является `true`, если метод получает права владения; в противном случае — `false`.

Класс `shared_timed_mutex` является *типом общего мьютекса с ограничением по времени* — типом, который соответствует требованиям типа общего мьютекса и типа мьютекса с ограничением по времени.

Тип общего мьютекса с ограничением по времени поддерживает дополнительные методы `try_lock_shared_for` и `try_lock_shared_until`:

- Метод `try_lock_shared_for` пытается получить совместное владение мьютексом до тех пор, пока не истечет период, заданный параметром. Если период не положительный, метод равен значению `try_lock_shared`. Этот метод не возвращает значение в течение заданного периода, если не получено совместное владение. Он возвращает значение `true`, если метод получает владение; в противном случае — значение `false`.

- Метод `try_lock_shared_until` пытается получить совместное владение мьютексом до тех пор, пока указанное абсолютное время не истечет. Если указанное время уже истекло, метод эквивалентен `try_lock_shared`. Этот метод не возвращает значение до указанного времени, если не получено совместное владение. Он возвращает значение `true`, если метод получает владение; в противном случае — значение `false`.

Класс шаблона `shared_lock` расширяет поддержку блокировки с ограничением времени и передает владение общему мьютексу. Владение мьютексом может быть получено на этапе создания или после и может быть передано другому объекту `shared_lock`. Объекты типа `shared_lock` можно переместить, но не копировать.

> [!WARNING]
> Типы синхронизации стандартной библиотеки C++, начиная с Visual Studio 2015 основаны на примитивах синхронизации Windows и больше не используют ConcRT (кроме случаев, когда целевой платформы Windows XP). Типы, определенные в &lt;shared_mutex > не должны использоваться с любой типами или функциями ConcRT.

## <a name="classes"></a>Классы

###  <a name="class_shared_mutex"></a> Класс shared_mutex

Класс `shared_mutex` реализует нерекурсивный мьютекс с семантикой совместного владения.

```cpp
class shared_mutex {
public:
   shared_mutex();
   ~shared_mutex();
   shared_mutex(const shared_mutex&) = delete;
   shared_mutex& operator=(const shared_mutex&) = delete;
   // Exclusive ownership
   void lock();
   // blocking
   bool try_lock();
   void unlock();
   // Shared ownership
   void lock_shared();
   // blocking
   bool try_lock_shared();
   void unlock_shared();
   // Getters
   typedef void** native_handle_type; // implementation defined
   native_handle_type native_handle();
   };
```

###  <a name="class_shared_timed_mutex"></a> Класс shared_timed_mutex

Класс `shared_timed_mutex` реализует нерекурсивный мьютекс с семантикой совместного владения, который соответствует требованиям типа мьютекса с ограничением по времени.

```cpp
class shared_timed_mutex {
public:
   shared_timed_mutex();
   ~shared_timed_mutex();
   shared_timed_mutex(const shared_timed_mutex&) = delete;
   shared_timed_mutex& operator=(const shared_timed_mutex&) = delete;
   // Exclusive ownership
   void lock();
   // blocking
   bool try_lock();
   template <class Rep, class Period>
   bool try_lock_for(const chrono::duration<Rep, Period>& rel_time);
   template <class Clock, class Duration>
   bool try_lock_until(const chrono::time_point<Clock, Duration>& abs_time);
   void unlock();
   // Shared ownership
   void lock_shared();
   // blocking
   bool try_lock_shared();
   template <class Rep, class Period>
   bool try_lock_shared_for(const chrono::duration<Rep, Period>& rel_time);
   template <class Clock, class Duration>
   bool try_lock_shared_until(const chrono::time_point<Clock, Duration>& abs_time);
   void unlock_shared();
   };
```

###  <a name="&lt;shared"></a> Класс shared_lock

Класс шаблонов `shared_lock` контролирует совместное владение объектом shared mutex в области. Параметр шаблона должен быть типом shared mutex.

```cpp
class shared_lock {
public:
   typedef Mutex mutex_type;
   shared_lock() noexcept;
   explicit shared_lock(mutex_type& m);
   // blocking
   shared_lock(mutex_type& m, defer_lock_t) noexcept;
   shared_lock(mutex_type& m, try_to_lock_t);
   shared_lock(mutex_type& m, adopt_lock_t);
   template <class Clock, class Duration>
   shared_lock(mutex_type& m,
   const chrono::time_point<Clock, Duration>& abs_time);
   template <class Rep, class Period>
   shared_lock(mutex_type& m,
   const chrono::duration<Rep, Period>& rel_time);
   ~shared_lock();
   shared_lock(shared_lock const&) = delete;
   shared_lock& operator=(shared_lock const&) = delete;
   shared_lock(shared_lock&& u) noexcept;
   shared_lock& operator=(shared_lock&& u) noexcept;
   void lock();
   // blocking
   bool try_lock();
   template <class Rep, class Period>
   bool try_lock_for(const chrono::duration<Rep, Period>& rel_time);
   template <class Clock, class Duration>
   bool try_lock_until(const chrono::time_point<Clock, Duration>& abs_time);
   void unlock();
   // Setters
   void swap(shared_lock& u) noexcept;
   mutex_type* release() noexcept;
   // Getters
   bool owns_lock() const noexcept;
   explicit operator bool () const noexcept;
   mutex_type* mutex() const noexcept;
private:
   mutex_type* pm; // exposition only
   bool owns; // exposition only
   };
```

## <a name="functions"></a>Функции

###  <a name="function_swap"></a> Поменять местами

Меняет местами объекты `shared_lock`.

```cpp
template <class Mutex>
void swap(shared_lock<Mutex>& x, shared_lock<Mutex>& y) noexcept;
```

Меняет местами содержимое объектов `shared_lock`. Фактически совпадает с `x.swap(y)`.

## <a name="requirements"></a>Требования

**Заголовок:** &lt;shared_mutex>

**Пространство имен:** std

## <a name="see-also"></a>См. также

[Файлы заголовка ссылаются](../standard-library/cpp-standard-library-header-files.md)
[&lt;мьютекс >](../standard-library/mutex.md)
