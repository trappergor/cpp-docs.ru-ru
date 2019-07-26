---
title: Класс recursive_mutex
ms.date: 11/04/2016
f1_keywords:
- mutex/std::recursive_mutex
- mutex/std::recursive_mutex::recursive_mutex
- mutex/std::recursive_mutex::lock
- mutex/std::recursive_mutex::try_lock
- mutex/std::recursive_mutex::unlock
ms.assetid: eb5ffd1b-7e78-4559-8391-bb220ead42fc
helpviewer_keywords:
- std::recursive_mutex [C++]
- std::recursive_mutex [C++], recursive_mutex
- std::recursive_mutex [C++], lock
- std::recursive_mutex [C++], try_lock
- std::recursive_mutex [C++], unlock
ms.openlocfilehash: 448b4d03e4d38dc45621cddab7d8f5d03b805968
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68451673"
---
# <a name="recursivemutex-class"></a>Класс recursive_mutex

Представляет *тип мьютекса*. В отличие от класса [mutex](../standard-library/mutex-class-stl.md), поведение вызовов методов блокировки для объектов, которые уже заблокированы, четко определено.

## <a name="syntax"></a>Синтаксис

```cpp
class recursive_mutex;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[recursive_mutex](#recursive_mutex)|Создает объект `recursive_mutex`.|
|[Деструктор ~recursive_mutex](#dtorrecursive_mutex_destructor)|Освобождает все ресурсы, используемые объектом `recursive_mutex`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[lock](#lock)|Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца мьютекса.|
|[try_lock](#try_lock)|Попытки получить права владельца мьютекса без блокировки.|
|[unlock](#unlock)|Освобождает права владения мьютексом.|

## <a name="requirements"></a>Требования

**Заголовок:** \<> мьютекса

**Пространство имен:** std

## <a name="lock"></a>  lock

Блокирует вызывающий поток до тех пор, пока этот поток не получит права владельца объекта `mutex`.

```cpp
void lock();
```

### <a name="remarks"></a>Примечания

Если вызывающий поток уже владеет `mutex`, метод немедленно возвращает значение и предыдущая блокировка остается в силе.

## <a name="recursive_mutex"></a>  recursive_mutex

Создает объект `recursive_mutex`, который не заблокирован.

```cpp
recursive_mutex();
```

## <a name="dtorrecursive_mutex_destructor"></a>  ~recursive_mutex

Освобождает все ресурсы, используемые объектом.

```cpp
~recursive_mutex();
```

### <a name="remarks"></a>Примечания

Если при выполнении деструктора объект заблокирован, поведение не определено.

## <a name="try_lock"></a>  try_lock

Попытки получить права владельца объекта `mutex` без блокировки.

```cpp
bool try_lock() noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если метод успешно получает владение `mutex` или если вызывающий `mutex**; otherwise, **false`поток уже владеет.

### <a name="remarks"></a>Примечания

Если вызывающий поток уже владеет `mutex`, функция немедленно возвращает **значение true**, а предыдущая блокировка остается в силе.

## <a name="unlock"></a>  unlock

Освобождает права владения мьютексом.

```cpp
void unlock();
```

### <a name="remarks"></a>Примечания

Этот метод освобождает владение `mutex` только после его вызова столько раз, сколько [lock](#lock) и [try_lock](#try_lock) были успешно вызваны для объекта`recursive_mutex`.

Если вызывающий поток не является владельцем `mutex`, поведение не определено.

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)\
[\<mutex>](../standard-library/mutex.md)
