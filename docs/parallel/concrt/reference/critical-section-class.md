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
ms.openlocfilehash: aef3ae6100133374cb89098f118c447effafd840
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424251"
---
# <a name="critical_section-class"></a>Класс critical_section

Не допускающий повторные входы мьютекс, который явно учитывает среду выполнения с параллелизмом.

## <a name="syntax"></a>Синтаксис

```cpp
class critical_section;
```

## <a name="members"></a>Члены

### <a name="public-typedefs"></a>Открытые определения типов

|Имя|Description|
|----------|-----------------|
|`native_handle_type`|Ссылка на объект `critical_section`.|

### <a name="public-classes"></a>Открытые классы

|Имя|Description|
|----------|-----------------|
|[Класс critical_section:: scoped_lock](#critical_section__scoped_lock_class)|Защищенная от исключения оболочка RAII для объекта `critical_section`.|

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[critical_section](#ctor)|Конструирует новую критическую секцию.|
|[Деструктор ~ critical_section](#dtor)|Уничтожает критическую секцию.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[lock](#lock)|Получает этот критический раздел.|
|[native_handle](#native_handle)|Возвращает собственный машинный код, зависящий от платформы, если он существует.|
|[try_lock](#try_lock)|Пытается получить блокировку без блокировки.|
|[try_lock_for](#try_lock_for)|Пытается получить блокировку без блокировки в течение указанного числа миллисекунд.|
|[unlock](#unlock)|Разблокирует критическую секцию.|

## <a name="remarks"></a>Remarks

Дополнительные сведения см. в разделе [структуры данных синхронизации](../../../parallel/concrt/synchronization-data-structures.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`critical_section`

## <a name="requirements"></a>Требования

**Заголовок:** ConcRT. h

**Пространство имен:** concurrency

## <a name="ctor"></a>critical_section

Конструирует новую критическую секцию.

```cpp
critical_section();
```

## <a name="dtor"></a>~ critical_section

Уничтожает критическую секцию.

```cpp
~critical_section();
```

### <a name="remarks"></a>Remarks

Ожидается, что блокировка больше не удерживается при выполнении деструктора. Разрешение критической секции, уничтожения с блокировкой, по-прежнему приводит к неопределенному поведению.

## <a name="lock"></a>скрыть

Получает этот критический раздел.

```cpp
void lock();
```

### <a name="remarks"></a>Remarks

Часто бывает безопаснее использовать конструкцию [scoped_lock](#critical_section__scoped_lock_class) для получения и освобождения `critical_section` объекта в безопасном для исключения виде.

Если блокировка уже удерживается вызывающим контекстом, будет выдано исключение [improper_lock](improper-lock-class.md) .

## <a name="native_handle"></a>native_handle

Возвращает собственный машинный код, зависящий от платформы, если он существует.

```cpp
native_handle_type native_handle();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на критическую секцию.

### <a name="remarks"></a>Remarks

Объект `critical_section` не связан с машинным обработчиком, зависящим от платформы, для операционной системы Windows. Метод просто возвращает ссылку на сам объект.

## <a name="critical_section__scoped_lock_class"></a>Класс critical_section:: scoped_lock

Защищенная от исключения оболочка RAII для объекта `critical_section`.

```cpp
class scoped_lock;
```

## <a name="critical_section__scoped_lock_ctor"></a>scoped_lock:: scoped_lock

Создает объект `scoped_lock` и получает объект `critical_section`, переданный в параметре `_Critical_section`. Если критическая секция удерживается другим потоком, этот вызов блокируется.

```cpp
explicit _CRTIMP scoped_lock(critical_section& _Critical_section);
```

### <a name="parameters"></a>Параметры

*_Critical_section*<br/>
Критическая секция для блокировки.

## <a name="critical_section__scoped_lock_dtor"></a>scoped_lock:: ~ scoped_lock

Уничтожает объект `scoped_lock` и освобождает критический раздел, указанный в его конструкторе.

```cpp
~scoped_lock();
```

## <a name="try_lock"></a>try_lock

Пытается получить блокировку без блокировки.

```cpp
bool try_lock();
```

### <a name="return-value"></a>Возвращаемое значение

Если блокировка была получена, значение **true**; в противном случае — значение **false**.

## <a name="try_lock_for"></a>try_lock_for

Пытается получить блокировку без блокировки в течение указанного числа миллисекунд.

```cpp
bool try_lock_for(unsigned int _Timeout);
```

### <a name="parameters"></a>Параметры

*_Timeout*<br/>
Количество миллисекунд перед истечением времени ожидания.

### <a name="return-value"></a>Возвращаемое значение

Если блокировка была получена, значение **true**; в противном случае — значение **false**.

## <a name="unlock"></a>блокирован

Разблокирует критическую секцию.

```cpp
void unlock();
```

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс reader_writer_lock](reader-writer-lock-class.md)
