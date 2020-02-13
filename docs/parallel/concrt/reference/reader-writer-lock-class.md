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
ms.openlocfilehash: 1a7386e527b5327d928bfdcb3281c88666f1b106
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77140853"
---
# <a name="reader_writer_lock-class"></a>Класс reader_writer_lock

Блокировка чтения или записи на основе очередей с предпочтением записи только с локальным вращением. Блокировка предоставляет модулям записи доступ в порядке поступления и блокирует доступ модулей чтения при постоянной нагрузке модулей записи.

## <a name="syntax"></a>Синтаксис

```cpp
class reader_writer_lock;
```

## <a name="members"></a>Члены

### <a name="public-classes"></a>Открытые классы

|Имя|Description|
|----------|-----------------|
|[Класс reader_writer_lock:: scoped_lock](#scoped_lock_class)|Потокобезопасная оболочка RAII, которую можно использовать для получения `reader_writer_lock` объектов блокировки в качестве модуля записи.|
|[Класс reader_writer_lock:: scoped_lock_read](#scoped_lock_read_class)|Потокобезопасная оболочка RAII, которую можно использовать для получения `reader_writer_lock` объектов блокировки в качестве читателя.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[reader_writer_lock](#ctor)|Создает новый объект `reader_writer_lock`.|
|[Деструктор ~ reader_writer_lock](#dtor)|Уничтожает объект `reader_writer_lock`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[lock](#lock)|Получает блокировку чтения-записи в качестве модуля записи.|
|[lock_read](#lock_read)|Получает блокировку чтения-записи в качестве читателя. При наличии модулей записи активные модули чтения должны подождать, пока они не будут выполнены. Читатель просто регистрирует интерес в блокировке и ждет, пока модули записи его освобождают.|
|[try_lock](#try_lock)|Пытается получить блокировку чтения-записи в качестве модуля записи без блокировки.|
|[try_lock_read](#try_lock_read)|Пытается получить блокировку чтения-записи в качестве читателя без блокировки.|
|[unlock](#unlock)|Разблокирует блокировку чтения-записи в зависимости от того, кто ее блокировал, читатель или модуль записи.|

## <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [структуры данных синхронизации](../../../parallel/concrt/synchronization-data-structures.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`reader_writer_lock`

## <a name="requirements"></a>Требования

**Заголовок:** ConcRT. h

**Пространство имен:** concurrency

## <a name="lock"></a>скрыть

Получает блокировку чтения-записи в качестве модуля записи.

```cpp
void lock();
```

### <a name="remarks"></a>Remarks

Часто безопаснее использовать конструкцию [scoped_lock](#scoped_lock_class) для получения и освобождения объекта `reader_writer_lock` в качестве средства записи в безопасном виде.

После того как средство записи пытается получить блокировку, все будущие читатели будут блокироваться до тех пор, пока средства записи не получат и не снимут блокировку. Эта блокировка перемещается на модули записи и может существенно замедлить считывание данных при непрерывной нагрузке модулей записи.

Модули записи помещаются в цепочку таким образом, что модуль записи, завершающий блокировку, освобождает следующий модуль записи в строке.

Если блокировка уже удерживается вызывающим контекстом, будет выдано исключение [improper_lock](improper-lock-class.md) .

## <a name="lock_read"></a>lock_read

Получает блокировку чтения-записи в качестве читателя. При наличии модулей записи активные модули чтения должны подождать, пока они не будут выполнены. Читатель просто регистрирует интерес в блокировке и ждет, пока модули записи его освобождают.

```cpp
void lock_read();
```

### <a name="remarks"></a>Remarks

Часто безопаснее использовать конструкцию [scoped_lock_read](#scoped_lock_read_class) для получения и освобождения объекта `reader_writer_lock` в качестве средства чтения в безопасном виде.

Если имеются модули записи, ожидающие блокировки, модуль чтения будет ожидать, пока все модули записи в строке не будут получены и освобождены. Эта блокировка перемещается на модули записи и может существенно замедлить считывание данных при непрерывной нагрузке модулей записи.

## <a name="ctor"></a>reader_writer_lock

Создает новый объект `reader_writer_lock`.

```cpp
reader_writer_lock();
```

## <a name="dtor"></a>~ reader_writer_lock

Уничтожает объект `reader_writer_lock`.

```cpp
~reader_writer_lock();
```

### <a name="remarks"></a>Remarks

Ожидается, что блокировка больше не удерживается при выполнении деструктора. Разрешение блокировки записи чтения на уничтожения с блокировкой по-прежнему приводит к неопределенному поведению.

## <a name="scoped_lock_class"></a>Класс reader_writer_lock:: scoped_lock

Потокобезопасная оболочка RAII, которую можно использовать для получения `reader_writer_lock` объектов блокировки в качестве модуля записи.

```cpp
class scoped_lock;
```

## <a name="scoped_lock_ctor"></a>scoped_lock:: scoped_lock

Создает объект `scoped_lock` и получает объект `reader_writer_lock`, переданный в параметре `_Reader_writer_lock`, в качестве модуля записи. Если блокировка удерживается другим потоком, этот вызов блокируется.

```cpp
explicit _CRTIMP scoped_lock(reader_writer_lock& _Reader_writer_lock);
```

### <a name="parameters"></a>Параметры

*_Reader_writer_lock*<br/>
Объект `reader_writer_lock`, который требуется получить в качестве модуля записи.

## <a name="scoped_lock_dtor"></a>scoped_lock:: ~ scoped_lock

Уничтожает объект `reader_writer_lock` и освобождает блокировку, заданную в его конструкторе.

```cpp
~scoped_lock();
```

## <a name="scoped_lock_read_class"></a>Класс reader_writer_lock:: scoped_lock_read

Потокобезопасная оболочка RAII, которую можно использовать для получения `reader_writer_lock` объектов блокировки в качестве читателя.

```cpp
class scoped_lock_read;
```

## <a name="scoped_lock_read_ctor"></a>scoped_lock_read:: scoped_lock_read

Создает объект `scoped_lock_read` и получает объект `reader_writer_lock`, переданный в параметре `_Reader_writer_lock`, как средство чтения. Если блокировка удерживается другим потоком в качестве модуля записи или ожидающих модулей записи, этот вызов блокируется.

```cpp
explicit _CRTIMP scoped_lock_read(reader_writer_lock& _Reader_writer_lock);
```

### <a name="parameters"></a>Параметры

*_Reader_writer_lock*<br/>
Объект `reader_writer_lock` для получения в качестве модуля чтения.

## <a name="a-namescoped_lock_read_dtor--reader_writer_lockscoped_lock_readscoped_lock_read-destructor"></a>Деструктор <a name="scoped_lock_read_dtor"> reader_writer_lock:: scoped_lock_read:: ~ scoped_lock_read

Уничтожает объект `scoped_lock_read` и освобождает блокировку, заданную в его конструкторе.

```cpp
~scoped_lock_read();
```

## <a name="try_lock"></a>try_lock

Пытается получить блокировку чтения-записи в качестве модуля записи без блокировки.

### <a name="syntax"></a>Синтаксис

```cpp
bool try_lock();
```

### <a name="return-value"></a>Возвращаемое значение

Если блокировка была получена, значение **true**; в противном случае — значение **false**.

## <a name="try_lock_read"></a>try_lock_read

Пытается получить блокировку чтения-записи в качестве читателя без блокировки.

```cpp
bool try_lock_read();
```

### <a name="return-value"></a>Возвращаемое значение

Если блокировка была получена, значение **true**; в противном случае — значение **false**.

## <a name="unlock"></a>блокирован

Разблокирует блокировку чтения-записи в зависимости от того, кто ее блокировал, читатель или модуль записи.

```cpp
void unlock();
```

### <a name="remarks"></a>Remarks

Если имеются модули записи, ожидающие блокировки, выпуск блокировки всегда будет переключаться к следующему модулю записи в порядке FIFO. Эта блокировка перемещается на модули записи и может существенно замедлить считывание данных при непрерывной нагрузке модулей записи.

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс critical_section](critical-section-class.md)
