---
title: Класс mutex (Стандартная библиотека C++ ) | Документы Майкрософт
ms.date: 11/04/2016
f1_keywords:
- mutex/std::mutex
- mutex/std::mutex::mutex
- mutex/std::mutex::lock
- mutex/std::mutex::native_handle
- mutex/std::mutex::try_lock
- mutex/std::mutex::unlock
ms.assetid: 7999d055-f74f-4303-810f-8d3c9cde2f69
helpviewer_keywords:
- std::mutex [C++]
- std::mutex [C++], mutex
- std::mutex [C++], lock
- std::mutex [C++], native_handle
- std::mutex [C++], try_lock
- std::mutex [C++], unlock
ms.openlocfilehash: 84e6e3a46903a204444df9886556ae2c563304a9
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81364848"
---
# <a name="mutex-class-c-standard-library"></a>Класс mutex (Стандартная библиотека C++)

Представляет *тип mutex*. Используйте объекты этого типа для принудительного взаимного исключения в программе.

## <a name="syntax"></a>Синтаксис

```cpp
class mutex;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[мьютекс](#mutex)|Формирует объект `mutex`.|
|[Деструктор mutex::~mutex](#dtormutex_destructor)|Освобождает ресурсы, используемые объектом `mutex`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[lock](#lock)|Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца объекта `mutex`.|
|[native_handle](#native_handle)|Возвращает тип реализации, представляющий дескриптор мьютекса.|
|[try_lock](#try_lock)|Попытки получить права владельца объекта `mutex` без блокировки.|
|[Разблокировать](#unlock)|Освобождает права владения объектом `mutex`.|

## <a name="requirements"></a>Требования

**Заголовок:** \<mutex>

**Пространство имен:** std

## <a name="mutexlock"></a><a name="lock"></a>mutex::lock

Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца объекта `mutex`.

```cpp
void lock();
```

### <a name="remarks"></a>Remarks

Если вызывающий поток уже является владельцем `mutex`, поведение не определено.

## <a name="mutexmutex-constructor"></a><a name="mutex"></a>mutex::mutex Конструктор

Создает объект `mutex`, который не заблокирован.

```cpp
constexpr mutex() noexcept;
```

## <a name="mutexmutex-destructor"></a><a name="dtormutex_destructor"></a>mutex:::-mutex Destructor

Освобождает все ресурсы, используемые объектом `mutex`.

```cpp
~mutex();
```

### <a name="remarks"></a>Remarks

Если при выполнении деструктора объект заблокирован, поведение не определено.

## <a name="mutexnative_handle"></a><a name="native_handle"></a>mutex::native_handle

Возвращает тип реализации, представляющий дескриптор мьютекса. Дескриптор мьютекса может использоваться разными способами в зависимости от реализации.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Возвращаемое значение

`native_handle_type`определяется как `Concurrency::critical_section *`, которое приводится к `void *`.

## <a name="mutextry_lock"></a><a name="try_lock"></a>mutex::try_lock

Попытки получить права владельца объекта `mutex` без блокировки.

```cpp
bool try_lock();
```

### <a name="return-value"></a>Возвращаемое значение

**верно,** если метод успешно получает `mutex`право собственности на ; в противном случае, **ложные**.

### <a name="remarks"></a>Remarks

Если вызывающий поток уже является владельцем `mutex`, поведение не определено.

## <a name="mutexunlock"></a><a name="unlock"></a>mutex::разблокировка

Освобождает права владения объектом `mutex`.

```cpp
void unlock();
```

### <a name="remarks"></a>Remarks

Если вызывающий поток не является владельцем `mutex`, поведение не определено.

## <a name="see-also"></a>См. также раздел

[Справка по файлам заголовка](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
