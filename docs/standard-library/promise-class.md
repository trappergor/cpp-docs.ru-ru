---
title: Класс promise | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
f1_keywords:
- future/std::promise
- future/std::promise::promise
- future/std::promise::get_future
- future/std::promise::set_exception
- future/std::promise::set_exception_at_thread_exit
- future/std::promise::set_value
- future/std::promise::set_value_at_thread_exit
- future/std::promise::swap
dev_langs:
- C++
ms.assetid: 2931558c-d94a-4ba1-ac4f-20bf7b6e23f9
author: corob-msft
ms.author: corob
helpviewer_keywords:
- std::promise [C++]
- std::promise [C++], promise
- std::promise [C++], get_future
- std::promise [C++], set_exception
- std::promise [C++], set_exception_at_thread_exit
- std::promise [C++], set_value
- std::promise [C++], set_value_at_thread_exit
- std::promise [C++], swap
ms.workload:
- cplusplus
ms.openlocfilehash: 8a1ddfd30a1e061426f0a19ac1118aa5ade1de17
ms.sourcegitcommit: 3614b52b28c24f70d90b20d781d548ef74ef7082
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/11/2018
ms.locfileid: "38958568"
---
# <a name="promise-class"></a>Класс promise

Описывает *асинхронный поставщик*.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
class promise;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание:|
|----------|-----------------|
|[Объект Promise](#promise)|Создает объект `promise`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[get_future](#get_future)|Возвращает [future](../standard-library/future-class.md), связанный с этим объектом promise.|
|[set_exception](#set_exception)|Атомарно устанавливает результат этого объекта promise для обозначения исключения.|
|[set_exception_at_thread_exit](#set_exception_at_thread_exit)|Атомарно устанавливает результат этого объекта promise для обозначения исключения и доставляет уведомление только после того, как все локальные объекты в текущем потоке уничтожены (обычно при выходе из потока).|
|[set_value](#set_value)|Атомарно устанавливает результат этого объекта promise для обозначения значения.|
|[set_value_at_thread_exit](#set_value_at_thread_exit)|Атомарно устанавливает результат этого объекта promise для обозначения значения и доставляет уведомление только после того, как все локальные объекты в текущем потоке уничтожены (обычно при выходе из потока).|
|[swap](#swap)|Выполняет обмен *связанного асинхронного состояния* этого объекта promise с состоянием указанного объекта promise.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[promise::operator=](#op_eq)|Назначение общего состояния этого объекта promise.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`promise`

## <a name="requirements"></a>Требования

**Заголовок:** \<будущих >

**Пространство имен:** std

## <a name="get_future"></a>  promise::get_future

Возвращает объект [future](../standard-library/future-class.md), который имеет то же самое *связанное асинхронное состояние*, что и данный объект promise.

```cpp
future<Ty> get_future();
```

### <a name="remarks"></a>Примечания

Если объект promise пустой, этот метод выдает [future_error](../standard-library/future-error-class.md) с [error_code](../standard-library/error-code-class.md) `no_state`.

Если этот метод уже вызывался для объекта promise с тем же самым связанным асинхронным состоянием, метод выдает `future_error` с `error_code` `future_already_retrieved`.

## <a name="op_eq"></a>  promise::operator=

Передает *связанное асинхронное состояние* от указанного объекта `promise`.

```cpp
promise& operator=(promise&& Other) noexcept;
```

### <a name="parameters"></a>Параметры

*Другие* A `promise` объекта.

### <a name="return-value"></a>Возвращаемое значение

`*this`

### <a name="remarks"></a>Примечания

Этот оператор передает связанное асинхронное состояние из *других*. После передачи *других* — *пустой*.

## <a name="promise"></a>  Конструктор promise::promise

Создает объект `promise`.

```cpp
promise();
template <class Alloc>
promise(allocator_arg_t, const Alloc& Al);
promise(promise&& Other) noexcept;
```

### <a name="parameters"></a>Параметры

*Al* распределитель памяти. Более подробную информацию см. в разделе [\<allocators>](../standard-library/allocators-header.md).

*Другие* A `promise` объекта.

### <a name="remarks"></a>Примечания

Первый конструктор создает *пустой*`promise` объект.

Второй конструктор создает пустой `promise` и использует *Al* для выделения памяти.

Третий конструктор создает `promise` и передает связанное асинхронное состояние из *других*и оставляет *других* пустой.

## <a name="set_exception"></a>  promise::set_exception

Автоматически сохраняет исключение в качестве результата объекта `promise` и устанавливает *связанное асинхронное состояние* в значение *ready*.

```cpp
void set_exception(exception_ptr Exc);
```

### <a name="parameters"></a>Параметры

*Исключенные* [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) сохраняется этим методом как результат исключения.

### <a name="remarks"></a>Примечания

Если объект `promise` не имеет связанного асинхронного состояния, этот метод выдает [future_error](../standard-library/future-error-class.md) с кодом ошибки `no_state`.

Если `set_exception`, [set_exception_at_thread_exit](#set_exception_at_thread_exit), [set_value](#set_value) или [set_value_at_thread_exit](#set_value_at_thread_exit) уже вызывались для объекта `promise`, который имеет то же самое связанное асинхронное состояние, то этот метод выдает `future_error` с кодом ошибки `promise_already_satisfied`.

В результате работы этого метода все потоки, которые заблокированы на связанном асинхронном состоянии, разблокируются.

## <a name="set_exception_at_thread_exit"></a>  promise::set_exception_at_thread_exit

Атомарно устанавливает результат `promise` для указания исключения, доставляя уведомление только после того, как все локальные объекты в текущем потоке уничтожены (обычно при завершении потока).

```cpp
void set_exception_at_thread_exit(exception_ptr Exc);
```

### <a name="parameters"></a>Параметры

*Исключенные* [exception_ptr](../standard-library/exception-typedefs.md#exception_ptr) сохраняется этим методом как результат исключения.

### <a name="remarks"></a>Примечания

Если объект promise не имеет *связанного асинхронного состояния*, этот метод выдает [future_error](../standard-library/future-error-class.md) с кодом ошибки `no_state`.

Если [set_exception](#set_exception), `set_exception_at_thread_exit`, [set_value](#set_value) или [set_value_at_thread_exit](#set_value_at_thread_exit) уже вызывались для объекта `promise`, имеющего то же самое связанное асинхронное состояние, то этот метод выдает `future_error` с кодом ошибки `promise_already_satisfied`.

В отличие от [set_exception](#set_exception) этот метод не устанавливает связанное асинхронное состояние в значение ready до тех пор, пока не будут уничтожены все локальные объекты в текущем потоке. Обычно потоки, которые заблокированы в связанном асинхронном состоянии, не разблокируются до завершения текущего потока.

## <a name="set_value"></a>  promise::set_value

Атомарно сохраняет значение в виде результата этого объекта `promise` и устанавливает *связанное асинхронное состояние* в значение *ready*.

```cpp
void promise::set_value(const Ty& Val);
void promise::set_value(Ty&& Val);
void promise<Ty&>::set_value(Ty& Val);
void promise<void>::set_value();
```

### <a name="parameters"></a>Параметры

*Val* значение, которое будет храниться как результат.

### <a name="remarks"></a>Примечания

Если объект `promise` не имеет связанного асинхронного состояния, этот метод выдает [future_error](../standard-library/future-error-class.md) с кодом ошибки `no_state`.

Если [set_exception](#set_exception), [set_exception_at_thread_exit](#set_exception_at_thread_exit) `set_value` или [set_value_at_thread_exit](#set_value_at_thread_exit) уже вызывались для объекта `promise`, имеющего то же самое связанное асинхронное состояние, то этот метод выдает `future_error` с кодом ошибки `promise_already_satisfied`.

В результате работы этого метода все потоки, которые заблокированы на связанном асинхронном состоянии, разблокируются.

Первый метод также выдает любое исключение, возникающее, когда *Val* копируется в связанном асинхронном состоянии. В этой ситуации связанное асинхронное состояние не устанавливается в значение ready.

Второй метод также выдает любое исключение, возникающее, когда *Val* перемещается в связанном асинхронном состоянии. В этой ситуации связанное асинхронное состояние не устанавливается в значение ready.

Для частичной специализации `promise<Ty&>`, сохраненное значение по сути является ссылкой на *Val*.

Для специализации `promise<void>` сохраненные значения не существуют.

## <a name="set_value_at_thread_exit"></a>  promise::set_value_at_thread_exit

Атомарно сохраняет значение в качестве результата этого объекта `promise`.

```cpp
void promise::set_value_at_thread_exit(const Ty& Val);
void promise::set_value_at_thread_exit(Ty&& Val);
void promise<Ty&>::set_value_at_thread_exit(Ty& Val);
void promise<void>::set_value_at_thread_exit();
```

### <a name="parameters"></a>Параметры

*Val* значение, которое будет храниться как результат.

### <a name="remarks"></a>Примечания

Если объект promise не имеет *связанного асинхронного состояния*, этот метод выдает [future_error](../standard-library/future-error-class.md) с кодом ошибки `no_state`.

Если [set_exception](#set_exception), [set_exception_at_thread_exit](#set_exception_at_thread_exit), [set_value](#set_value) или `set_value_at_thread_exit` уже вызывались для объекта `promise`, имеющего то же самое связанное асинхронное состояние, этот метод выдает `future_error` с кодом ошибки `promise_already_satisfied`.

В отличие от `set_value` связанное асинхронное состояние не устанавливается в значение ready до тех пор, пока все локальные объекты текущего потока не будут уничтожены. Обычно потоки, которые заблокированы в связанном асинхронном состоянии, не разблокируются до завершения текущего потока.

Первый метод также выдает любое исключение, возникающее, когда *Val* копируется в связанном асинхронном состоянии.

Второй метод также выдает любое исключение, возникающее, когда *Val* перемещается в связанном асинхронном состоянии.

Для частичной специализации `promise<Ty&>`, хранимое значение является ссылкой на *Val*.

Для специализации `promise<void>` сохраненные значения не существуют.

## <a name="swap"></a>  promise::swap

Обменивает *связанное асинхронное состояние* данного объекта promise с состоянием указанного объекта.

```cpp
void swap(promise& Other) noexcept;
```

### <a name="parameters"></a>Параметры

*Другие* A `promise` объекта.

## <a name="see-also"></a>См. также

[Справочник по файлам заголовков](../standard-library/cpp-standard-library-header-files.md)<br/>
