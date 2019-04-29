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
ms.openlocfilehash: f334b159ae39f48006a135c6e36d413b737a7344
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62296167"
---
# <a name="criticalsection-class"></a>Класс critical_section

Не допускающий повторные входы мьютекс, который явно учитывает среду выполнения с параллелизмом.

## <a name="syntax"></a>Синтаксис

```
class critical_section;
```

## <a name="members"></a>Участники

### <a name="public-typedefs"></a>Общедоступные определения типов

|name|Описание|
|----------|-----------------|
|`native_handle_type`|Ссылка на объект `critical_section`.|

### <a name="public-classes"></a>Открытые классы

|name|Описание|
|----------|-----------------|
|[Класс critical_section::scoped_lock](#critical_section__scoped_lock_class)|Исключение безопасная оболочка RAII для `critical_section` объекта.|

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[critical_section](#ctor)|Создает новый критический раздел.|
|[~ critical_section деструктор](#dtor)|Уничтожает критический раздел.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[lock](#lock)|Получает данную критическую секцию.|
|[native_handle](#native_handle)|Возвращает конкретный собственный дескриптор платформы, если он существует.|
|[try_lock](#try_lock)|Пытается получить блокировку без блокировки.|
|[try_lock_for](#try_lock_for)|Пытается получить блокировку без блокировки в течение указанного числа миллисекунд.|
|[unlock](#unlock)|Снимает блокировку критической секции.|

## <a name="remarks"></a>Примечания

Дополнительные сведения см. в разделе [структуры данных синхронизации](../../../parallel/concrt/synchronization-data-structures.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`critical_section`

## <a name="requirements"></a>Требования

**Заголовок:** concrt.h

**Пространство имен:** concurrency

##  <a name="ctor"></a> critical_section

Создает новый критический раздел.

```
critical_section();
```

##  <a name="dtor"></a> ~ critical_section

Уничтожает критический раздел.

```
~critical_section();
```

### <a name="remarks"></a>Примечания

Предполагается, что больше не блокировку при выполнении деструктора. По-прежнему позволяя критический раздел для уничтожения с блокировкой содержатся результаты в приведет к неопределенному поведению.

##  <a name="lock"></a> Блокировки

Получает данную критическую секцию.

```
void lock();
```

### <a name="remarks"></a>Примечания

Часто лучше использовать [scoped_lock](#critical_section__scoped_lock_class) конструкции для получения и освобождения `critical_section` объекта к исключению безопасным способом.

Если вызывающий контекст уже удерживается блокировка [improper_lock](improper-lock-class.md) будет создано исключение.

##  <a name="native_handle"></a> native_handle

Возвращает конкретный собственный дескриптор платформы, если он существует.

```
native_handle_type native_handle();
```

### <a name="return-value"></a>Возвращаемое значение

Ссылка на критический раздел.

### <a name="remarks"></a>Примечания

Объект `critical_section` объект не связан с определенной собственный дескриптор платформы для операционной системы Windows. Метод просто возвращает ссылку на сам объект.

##  <a name="critical_section__scoped_lock_class"></a>  Класс critical_section::scoped_lock

Исключение безопасная оболочка RAII для `critical_section` объекта.

```
class scoped_lock;
```

##  <a name="critical_section__scoped_lock_ctor"></a> scoped_lock::scoped_lock

Создает `scoped_lock` объекта и получает `critical_section` переданный объект `_Critical_section` параметра. Если критический раздел удерживается другим потоком, этот вызов блокируется.

```
explicit _CRTIMP scoped_lock(critical_section& _Critical_section);
```

### <a name="parameters"></a>Параметры

*_Critical_section*<br/>
Критический раздел для блокировки.

##  <a name="critical_section__scoped_lock_dtor"></a> scoped_lock:: ~ scoped_lock

Уничтожает `scoped_lock` объект и освобождает критический раздел, переданную в конструкторе.

```
~scoped_lock();
```

##  <a name="try_lock"></a> try_lock

Пытается получить блокировку без блокировки.

```
bool try_lock();
```

### <a name="return-value"></a>Возвращаемое значение

Если блокировка была получена, значение **true**; в противном случае значение **false**.

##  <a name="try_lock_for"></a> try_lock_for

Пытается получить блокировку без блокировки в течение указанного числа миллисекунд.

```
bool try_lock_for(unsigned int _Timeout);
```

### <a name="parameters"></a>Параметры

*_Timeout*<br/>
Количество миллисекунд перед истечением времени ожидания.

### <a name="return-value"></a>Возвращаемое значение

Если блокировка была получена, значение **true**; в противном случае значение **false**.

##  <a name="unlock"></a> разблокировать

Снимает блокировку критической секции.

```
void unlock();
```

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[Класс reader_writer_lock](reader-writer-lock-class.md)
