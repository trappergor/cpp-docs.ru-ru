---
title: Класс critical_section
ms.date: 11/04/2016
f1_keywords:
- critical_section
- CONCRT/concurrency::critical_section
- CONCRT/concurrency::critical_section::critical_section::scoped_lock Class
- CONCRT/concurrency::critical_section::critical_section
- CONCRT/concurrency::critical_section::lock
- CONCRT/concurrency::critical_section::native_handle
- CONCRT/concurrency::critical_section::try_lock
- CONCRT/concurrency::critical_section::try_lock_for
- CONCRT/concurrency::critical_section::unlock
helpviewer_keywords:
- critical_section class
ms.assetid: fa3c89d6-be5d-4d1b-bddb-8232814e6cf6
ms.openlocfilehash: 24f96282a7728c6db6e0b05d36406f15383913f3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81372679"
---
# <a name="critical_section-class"></a>Класс critical_section

Не допускающий повторные входы мьютекс, который явно учитывает среду выполнения с параллелизмом.

## <a name="syntax"></a>Синтаксис

```cpp
class critical_section;
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|Имя|Описание|
|----------|-----------------|
|`native_handle_type`|Ссылка на объект `critical_section`.|

### <a name="public-classes"></a>Открытые классы

|Имя|Описание|
|----------|-----------------|
|[Класс critical_section::scoped_lock](#critical_section__scoped_lock_class)|Безопасная обертка RAII `critical_section` для объекта.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[critical_section](#ctor)|Строит новый критический раздел.|
|[«critical_section деструктор](#dtor)|Уничтожает критический раздел.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[lock](#lock)|Приобретает этот критический раздел.|
|[native_handle](#native_handle)|Возвращает конкретную родную ручку платформы, если она существует.|
|[try_lock](#try_lock)|Пытается приобрести замок без блокировки.|
|[try_lock_for](#try_lock_for)|Пытается получить блокировку без блокировки в течение указанного числа миллисекунд.|
|[Разблокировать](#unlock)|Разблокирует критический раздел.|

## <a name="remarks"></a>Remarks

Для получения дополнительной [Synchronization Data Structures](../../../parallel/concrt/synchronization-data-structures.md)информации см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`critical_section`

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

**Название:** параллелизм

## <a name="critical_section"></a><a name="ctor"></a>Critical_section

Строит новый критический раздел.

```cpp
critical_section();
```

## <a name="critical_section"></a><a name="dtor"></a>(critical_section

Уничтожает критический раздел.

```cpp
~critical_section();
```

### <a name="remarks"></a>Remarks

Ожидается, что блокировка больше не удерживается при запуске деструктора. Разрешение критическим сечениям разрушаться с блокировкой, удерживаемой, приводит к неопределенному поведению.

## <a name="lock"></a><a name="lock"></a>Блокировки

Приобретает этот критический раздел.

```cpp
void lock();
```

### <a name="remarks"></a>Remarks

Часто безопаснее использовать [scoped_lock](#critical_section__scoped_lock_class) конструкцию для `critical_section` безопасного приобретения и выпуска объекта в порядке исключения.

Если блокировка уже удерживается контекстом вызова, будет брошено [improper_lock](improper-lock-class.md) исключение.

## <a name="native_handle"></a><a name="native_handle"></a>native_handle

Возвращает конкретную родную ручку платформы, если она существует.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на критический раздел.

### <a name="remarks"></a>Remarks

Объект `critical_section` не связан с конкретной нативной ручкой платформы для операционной системы Windows. Метод просто возвращает ссылку на сам объект.

## <a name="critical_sectionscoped_lock-class"></a><a name="critical_section__scoped_lock_class"></a>critical_section::scoped_lock класс

Безопасная обертка RAII `critical_section` для объекта.

```cpp
class scoped_lock;
```

## <a name="scoped_lockscoped_lock"></a><a name="critical_section__scoped_lock_ctor"></a>scoped_lock::scoped_lock

Строит `scoped_lock` объект и приобретает `critical_section` объект, пройденый по параметру. `_Critical_section` Если критический раздел удерживается другим потоком, этот вызов будет блокироваться.

```cpp
explicit _CRTIMP scoped_lock(critical_section& _Critical_section);
```

### <a name="parameters"></a>Параметры

*_Critical_section*<br/>
Критический раздел для блокировки.

## <a name="scoped_lockscoped_lock"></a><a name="critical_section__scoped_lock_dtor"></a>scoped_lock::-scoped_lock

Уничтожает `scoped_lock` объект и выпускает критический участок, поставляемый в его конструктор.

```cpp
~scoped_lock();
```

## <a name="try_lock"></a><a name="try_lock"></a>Try_lock

Пытается приобрести замок без блокировки.

```cpp
bool try_lock();
```

### <a name="return-value"></a>Возвращаемое значение

Если замок был приобретен, значение **верно**; в противном случае значение **ложное.**

## <a name="try_lock_for"></a><a name="try_lock_for"></a>try_lock_for

Пытается получить блокировку без блокировки в течение указанного числа миллисекунд.

```cpp
bool try_lock_for(unsigned int _Timeout);
```

### <a name="parameters"></a>Параметры

*_Timeout*<br/>
Количество миллисекунд перед истечением времени ожидания.

### <a name="return-value"></a>Возвращаемое значение

Если замок был приобретен, значение **верно**; в противном случае значение **ложное.**

## <a name="unlock"></a><a name="unlock"></a>Разблокировать

Разблокирует критический раздел.

```cpp
void unlock();
```

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[класс reader_writer_lock](reader-writer-lock-class.md)
