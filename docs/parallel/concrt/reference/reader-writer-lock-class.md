---
title: Класс reader_writer_lock
ms.date: 11/04/2016
f1_keywords:
- reader_writer_lock
- CONCRT/concurrency::reader_writer_lock
- CONCRT/concurrency::reader_writer_lock::scoped_lock
- CONCRT/concurrency::reader_writer_lock::scoped_lock_read
- CONCRT/concurrency::reader_writer_lock::reader_writer_lock
- CONCRT/concurrency::reader_writer_lock::lock
- CONCRT/concurrency::reader_writer_lock::lock_read
- CONCRT/concurrency::reader_writer_lock::try_lock
- CONCRT/concurrency::reader_writer_lock::try_lock_read
- CONCRT/concurrency::reader_writer_lock::unlock
helpviewer_keywords:
- reader_writer_lock class
ms.assetid: 91a59cd2-ca05-4b74-8398-d826d9f86736
ms.openlocfilehash: 13b44387f3e9489090ec31345fe4347ff5f205ca
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81376240"
---
# <a name="reader_writer_lock-class"></a>Класс reader_writer_lock

Блокировка чтения или записи на основе очередей с предпочтением записи только с локальным вращением. Блокировка предоставляет модулям записи доступ в порядке поступления и блокирует доступ модулей чтения при постоянной нагрузке модулей записи.

## <a name="syntax"></a>Синтаксис

```cpp
class reader_writer_lock;
```

## <a name="members"></a>Участники

### <a name="public-classes"></a>Открытые классы

|Имя|Описание|
|----------|-----------------|
|[Класс reader_writer_lock::scoped_lock](#scoped_lock_class)|Безопасная обертка RAII, которая `reader_writer_lock` может быть использована для приобретения объектов блокировки в качестве писателя.|
|[Класс reader_writer_lock::scoped_lock_read](#scoped_lock_read_class)|Безопасная обертка RAII, которая `reader_writer_lock` может быть использована для приобретения объектов блокировки в качестве считывателя.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[reader_writer_lock](#ctor)|Создает новый объект `reader_writer_lock`.|
|[«reader_writer_lock деструктор](#dtor)|Уничтожает `reader_writer_lock` объект.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[lock](#lock)|Приобретает замок читателя-писателя как писатель.|
|[lock_read](#lock_read)|Приобретает замок читателя-писателя в качестве читателя. Если есть писатели, активные читатели должны ждать, пока они не будут сделаны. Читатель просто регистрирует интерес к блокировке и ждет, когда писатели его выпустят.|
|[try_lock](#try_lock)|Попытки приобрести блокировку читателя-писателя как писателя без блокировки.|
|[try_lock_read](#try_lock_read)|Попытки приобрести блокировку читателя-писателя в качестве читателя без блокировки.|
|[Разблокировать](#unlock)|Открывает блокировку читателя-писателя в зависимости от того, кто его заблокировал, читатель или писатель.|

## <a name="remarks"></a>Remarks

Для получения дополнительной [Synchronization Data Structures](../../../parallel/concrt/synchronization-data-structures.md)информации см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`reader_writer_lock`

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

**Название:** параллелизм

## <a name="lock"></a><a name="lock"></a>Блокировки

Приобретает замок читателя-писателя как писатель.

```cpp
void lock();
```

### <a name="remarks"></a>Remarks

Часто безопаснее использовать [scoped_lock](#scoped_lock_class) конструкцию для `reader_writer_lock` приобретения и выпуска объекта в качестве автора в качестве безопасного исключения.

После того как средство записи пытается получить блокировку, все будущие читатели будут блокироваться до тех пор, пока средства записи не получат и не снимут блокировку. Этот замок предвзято к сочинителям и может голодать читателей под непрерывной нагрузкой сочинителей.

Писатели прикованы так, что писатель выхода блокировки релизы следующего писателя в линии.

Если блокировка уже удерживается контекстом вызова, будет брошено [improper_lock](improper-lock-class.md) исключение.

## <a name="lock_read"></a><a name="lock_read"></a>lock_read

Приобретает замок читателя-писателя в качестве читателя. Если есть писатели, активные читатели должны ждать, пока они не будут сделаны. Читатель просто регистрирует интерес к блокировке и ждет, когда писатели его выпустят.

```cpp
void lock_read();
```

### <a name="remarks"></a>Remarks

Часто безопаснее использовать [scoped_lock_read](#scoped_lock_read_class) конструкцию для `reader_writer_lock` приобретения и выпуска объекта в качестве читателя безопасным способом исключения.

Если есть писатели, ожидающие на блокировке, читатель будет ждать, пока все писатели в очереди приобрели и выпустили блокировку. Этот замок предвзято к сочинителям и может голодать читателей под непрерывной нагрузкой сочинителей.

## <a name="reader_writer_lock"></a><a name="ctor"></a>reader_writer_lock

Создает новый объект `reader_writer_lock`.

```cpp
reader_writer_lock();
```

## <a name="reader_writer_lock"></a><a name="dtor"></a>(reader_writer_lock

Уничтожает `reader_writer_lock` объект.

```cpp
~reader_writer_lock();
```

### <a name="remarks"></a>Remarks

Ожидается, что блокировка больше не удерживается при запуске деструктора. Разрешение блокировке писателя читателя разрушаться с блокировкой по-прежнему удерживается приводит к неопределенным поведением.

## <a name="reader_writer_lockscoped_lock-class"></a><a name="scoped_lock_class"></a>reader_writer_lock::scoped_lock класс

Безопасная обертка RAII, которая `reader_writer_lock` может быть использована для приобретения объектов блокировки в качестве писателя.

```cpp
class scoped_lock;
```

## <a name="scoped_lockscoped_lock"></a><a name="scoped_lock_ctor"></a>scoped_lock::scoped_lock

Строит `scoped_lock` объект и приобретает `reader_writer_lock` объект, передаваемый в параметре `_Reader_writer_lock` в качестве писателя. Если блокировка удерживается другим потоком, этот вызов будет блокироваться.

```cpp
explicit _CRTIMP scoped_lock(reader_writer_lock& _Reader_writer_lock);
```

### <a name="parameters"></a>Параметры

*_Reader_writer_lock*<br/>
Объект `reader_writer_lock` приобрести в качестве писателя.

## <a name="scoped_lockscoped_lock"></a><a name="scoped_lock_dtor"></a>scoped_lock::-scoped_lock

Уничтожает `reader_writer_lock` объект и освобождает замок, поставляемый в его конструктор.

```cpp
~scoped_lock();
```

## <a name="reader_writer_lockscoped_lock_read-class"></a><a name="scoped_lock_read_class"></a>reader_writer_lock::scoped_lock_read класс

Безопасная обертка RAII, которая `reader_writer_lock` может быть использована для приобретения объектов блокировки в качестве считывателя.

```cpp
class scoped_lock_read;
```

## <a name="scoped_lock_readscoped_lock_read"></a><a name="scoped_lock_read_ctor"></a>scoped_lock_read::scoped_lock_read

Строит `scoped_lock_read` объект и приобретает `reader_writer_lock` объект, передаваемый в параметре `_Reader_writer_lock` в качестве считывателя. Если блокировка удерживается другим потоком в качестве автора или находится в ожидании авторов, этот вызов будет заблокирован.

```cpp
explicit _CRTIMP scoped_lock_read(reader_writer_lock& _Reader_writer_lock);
```

### <a name="parameters"></a>Параметры

*_Reader_writer_lock*<br/>
Объект `reader_writer_lock` приобретается как читатель.

## <a name="a-namescoped_lock_read_dtor--reader_writer_lockscoped_lock_readscoped_lock_read-destructor"></a><a name="scoped_lock_read_dtor">reader_writer_lock:::scoped_lock_read:: Scoped_lock_read Деструктор

Уничтожает `scoped_lock_read` объект и освобождает замок, поставляемый в его конструктор.

```cpp
~scoped_lock_read();
```

## <a name="try_lock"></a><a name="try_lock"></a>Try_lock

Попытки приобрести блокировку читателя-писателя как писателя без блокировки.

### <a name="syntax"></a>Синтаксис

```cpp
bool try_lock();
```

### <a name="return-value"></a>Возвращаемое значение

Если замок был приобретен, значение **верно**; в противном случае значение **ложное.**

## <a name="try_lock_read"></a><a name="try_lock_read"></a>try_lock_read

Попытки приобрести блокировку читателя-писателя в качестве читателя без блокировки.

```cpp
bool try_lock_read();
```

### <a name="return-value"></a>Возвращаемое значение

Если замок был приобретен, значение **верно**; в противном случае значение **ложное.**

## <a name="unlock"></a><a name="unlock"></a>Разблокировать

Открывает блокировку читателя-писателя в зависимости от того, кто его заблокировал, читатель или писатель.

```cpp
void unlock();
```

### <a name="remarks"></a>Remarks

Если есть писатели, ожидающие на блокировке, освобождение блокировки всегда будет идти к следующему писателю в порядке FIFO. Этот замок предвзято к сочинителям и может голодать читателей под непрерывной нагрузкой сочинителей.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс critical_section](critical-section-class.md)
