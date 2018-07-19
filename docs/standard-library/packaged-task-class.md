---
title: Класс packaged_task | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- future/std::packaged_task
- future/std::packaged_task::packaged_task
- future/std::packaged_task::get_future
- future/std::packaged_task::make_ready_at_thread_exit
- future/std::packaged_task::reset
- future/std::packaged_task::swap
- future/std::packaged_task::valid
- future/std::packaged_task::operator()
- future/std::packaged_task::operator bool
dev_langs:
- C++
ms.assetid: 0a72cbe3-f22a-4bfe-8e50-dcb268c98780
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::packaged_task [C++]
- std::packaged_task [C++], packaged_task
- std::packaged_task [C++], get_future
- std::packaged_task [C++], make_ready_at_thread_exit
- std::packaged_task [C++], reset
- std::packaged_task [C++], swap
- std::packaged_task [C++], valid
ms.workload:
- cplusplus
ms.openlocfilehash: 7eb5b8d003682f5b941dd805f424afbe4a36cc85
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38964799"
---
# <a name="packagedtask-class"></a>Класс packaged_task

Описывает *асинхронный поставщик*, который является оберткой вызова с сигнатурой вызова `Ty(ArgTypes...)`. Его *связанное асинхронное состояние* хранит копию его вызываемого объекта, помимо возможных результатов.

## <a name="syntax"></a>Синтаксис

```cpp
template <class>
class packaged_task;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[деструктор packaged_task](#packaged_task)|Создает объект `packaged_task`.|
|[Деструктор packaged_task::~packaged_task](#dtorpackaged_task_destructor)|Уничтожает объект `packaged_task`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[get_future](#get_future)|Возвращает объект [future](../standard-library/future-class.md), который имеет то же связанное асинхронное состояние.|
|[make_ready_at_thread_exit](#make_ready_at_thread_exit)|Вызывает вызываемый объект, который хранится в связанном асинхронном состоянии и атомарно сохраняет возвращаемое значение.|
|[reset](#reset)|Заменяет связанное асинхронное состояние.|
|[swap](#swap)|Меняет местами связанное асинхронное состояние с состоянием указанного объекта.|
|[допустимый](#valid)|Указывает, имеет ли объект связанное асинхронное состояние.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[packaged_task::operator=](#op_eq)|Передает связанное асинхронное состояние из указанного объекта.|
|[packaged_task::operator()](#op_call)|Вызывает вызываемый объект, который хранится в связанном асинхронном состоянии, атомарно сохраняет возвращаемое значение и устанавливает состояние в значение *ready*.|
|[packaged_task::operator bool](#op_bool)|Указывает, имеет ли объект связанное асинхронное состояние.|

## <a name="requirements"></a>Требования

**Заголовок:** \<будущих >

**Пространство имен:** std

## <a name="get_future"></a>  packaged_task::get_future

Возвращает объект типа `future<Ty>`, который имеет то же самое *связанное асинхронное состояние*.

```cpp
future<Ty> get_future();
```

### <a name="remarks"></a>Примечания

Если объект `packaged_task` не имеет связанного асинхронного состояния, этот метод выдает [future_error](../standard-library/future-error-class.md) с кодом ошибки `no_state`.

Если этот метод уже был вызван для объекта `packaged_task`, который имеет то же самое асинхронное состояние, этот метод выдает `future_error` с кодом ошибки `future_already_retrieved`.

## <a name="make_ready_at_thread_exit"></a>  packaged_task::make_ready_at_thread_exit

Вызывает вызываемый объект, который хранится в *связанном асинхронном состоянии* и атомарно сохраняет возвращаемое значение.

```cpp
void make_ready_at_thread_exit(ArgTypes... args);
```

### <a name="remarks"></a>Примечания

Если объект `packaged_task` не имеет связанного асинхронного состояния, этот метод выдает [future_error](../standard-library/future-error-class.md) с кодом ошибки `no_state`.

Если этот метод или [make_ready_at_thread_exit](#make_ready_at_thread_exit) уже был вызван для объекта `packaged_task`, который имеет то же самое связанное асинхронное состояние, этот метод выдает `future_error` с кодом ошибки `promise_already_satisfied`.

В противном случае этот оператор вызывает `INVOKE(fn, args..., Ty)`, где *fn* — вызываемый объект, который хранится в связанном асинхронном состоянии. Любое возвращаемое значение атомарно сохраняется как возвращенный результат связанного асинхронного состояния.

В отличие от [packaged_task:: operator()](#op_call) связанное асинхронное состояние не устанавливается в `ready`, пока не будут уничтожены все локальные объекты потока в вызывающем потоке. Обычно потоки, которые заблокированы в связанном асинхронном состоянии, не разблокируются до выхода из вызывающего потока.

## <a name="op_eq"></a>  packaged_task::operator=

Передает *связанное асинхронное состояние* из указанного объекта.

```cpp
packaged_task& operator=(packaged_task&& Right);
```

### <a name="parameters"></a>Параметры

*Справа* A `packaged_task` объекта.

### <a name="return-value"></a>Возвращаемое значение

`*this`

### <a name="remarks"></a>Примечания

После выполнения операции *справа* больше не имеет связанного асинхронного состояния.

## <a name="op_call"></a>  packaged_task::operator()

Вызывает вызываемый объект, который хранится в *связанном асинхронном состоянии*, атомарно сохраняет возвращаемое значение и устанавливает состояние в значение *ready*.

```cpp
void operator()(ArgTypes... args);
```

### <a name="remarks"></a>Примечания

Если объект `packaged_task` не имеет связанного асинхронного состояния, этот метод выдает [future_error](../standard-library/future-error-class.md) с кодом ошибки `no_state`.

Если этот метод или [make_ready_at_thread_exit](#make_ready_at_thread_exit) уже был вызван для объекта `packaged_task`, который имеет то же самое связанное асинхронное состояние, этот метод выдает `future_error` с кодом ошибки `promise_already_satisfied`.

В противном случае этот оператор вызывает `INVOKE(fn, args..., Ty)`, где *fn* — вызываемый объект, который хранится в связанном асинхронном состоянии. Любое возвращаемое значение атомарно сохраняется как возвращенный результат связанного асинхронного состояния, и состояние устанавливается в значение ready. В результате все потоки, которые заблокированы на связанном асинхронном состоянии, разблокируются.

## <a name="op_bool"></a>  packaged_task::operator bool

Указывает, имеет ли объект `associated asynchronous state`.

```cpp
operator bool() const noexcept;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если объект имеет связанное асинхронное состояние; в противном случае **false**.

## <a name="packaged_task"></a>  Конструктор packaged_task::packaged_task

Создает объект `packaged_task`.

```cpp
packaged_task() noexcept;
packaged_task(packaged_task&& Right) noexcept;
template <class Fn>
   explicit packaged_task(Fn&& fn);

template <class Fn, class Alloc>
   explicit packaged_task(
      allocator_arg_t, const Alloc& alloc, Fn&& fn);
```

### <a name="parameters"></a>Параметры

*Справа* A `packaged_task` объекта.

*Alloc* распределитель памяти. Дополнительные сведения см. в разделе [\<allocators>](../standard-library/allocators-header.md).

*fn* объект функции.

### <a name="remarks"></a>Примечания

Первый конструктор создает объект `packaged_task`, который не имеет *связанного асинхронного состояния*.

Второй конструктор создает `packaged_task` и передает связанное асинхронное состояние из *справа*. После выполнения операции *справа* больше не имеет связанного асинхронного состояния.

Третий конструктор создает `packaged_task` объект, имеющий копию *fn* хранящиеся в его связанном асинхронном состоянии.

Четвертый конструктор создает `packaged_task` объект, имеющий копию *fn* хранятся в его связанном асинхронном состоянии и использует `alloc` для выделения памяти.

## <a name="dtorpackaged_task_destructor"></a> Деструктор packaged_task::~packaged_task

Уничтожает объект `packaged_task`.

```cpp
~packaged_task();
```

### <a name="remarks"></a>Примечания

Если *связанное асинхронное состояние* отлично от значения *ready*, деструктор сохраняет исключение [future_error](../standard-library/future-error-class.md) с кодом ошибки `broken_promise` в качестве результата в связанное асинхронное состояние. Все потоки, которые заблокированы на связанное асинхронное состояние, разблокируются.

## <a name="reset"></a>  packaged_task::reset

Использует новое *связанное асинхронное состояние* для замены существующего связанного асинхронного состояния.

```cpp
void reset();
```

### <a name="remarks"></a>Примечания

По сути, этот метод выполняет `*this = packaged_task(move(fn))`, где *fn* является объектом функции, который хранится в связанном асинхронном состоянии для данного объекта. Таким образом, состояние объекта очищается и [get_future](#get_future), [operator()](#op_call) и [make_ready_at_thread_exit](#make_ready_at_thread_exit) можно вызывать как на вновь созданный объект.

## <a name="swap"></a>  packaged_task::swap

Меняет местами связанное асинхронное состояние с состоянием указанного объекта.

```cpp
void swap(packaged_task& Right) noexcept;
```

### <a name="parameters"></a>Параметры

*Справа* A `packaged_task` объекта.

## <a name="valid"></a>  packaged_task::valid

Указывает, имеет ли объект `associated asynchronous state`.

```cpp
bool valid() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если объект имеет связанное асинхронное состояние; в противном случае **false**.

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
[\<future>](../standard-library/future.md)<br/>
