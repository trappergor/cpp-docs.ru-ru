---
title: Класс completion_future
ms.date: 11/04/2016
f1_keywords:
- completion_future
- AMPRT/completion_future
- AMPRT/Concurrency::completion_future::completion_future
- AMPRT/Concurrency::completion_future::get
- AMPRT/Concurrency::completion_future::then
- AMPRT/Concurrency::completion_future::to_task
- AMPRT/Concurrency::completion_future::valid
- AMPRT/Concurrency::completion_future::wait
- AMPRT/Concurrency::completion_future::wait_for
- AMPRT/Concurrency::completion_future::wait_until
ms.assetid: 1303c62e-546d-4b02-a578-251ed3fc0b6b
ms.openlocfilehash: 69aacad02df5290f161e9d8d311be347668be9f9
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127024"
---
# <a name="completion_future-class"></a>Класс completion_future

Представляет будущее, соответствующее асинхронной C++ операции amp.

## <a name="syntax"></a>Синтаксис

```cpp
class completion_future;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Конструктор completion_future](#ctor)|Инициализирует новый экземпляр класса `completion_future`.|
|[Деструктор ~ completion_future](#dtor)|Уничтожает объект `completion_future`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[get](#get)|Ожидает завершения связанной асинхронной операции.|
|[этого](#then)|Повязывает объект функции обратного вызова к `completion_future` объекту, который будет выполнен, когда связанная асинхронная операция завершает выполнение.|
|[to_task](#to_task)|Возвращает объект `task`, соответствующий связанной асинхронной операции.|
|[допустимым](#valid)|Возвращает логическое значение, указывающее, связан ли объект с асинхронной операцией.|
|[ожидания](#wait)|Блокируется до завершения связанной асинхронной операции.|
|[wait_for](#wait_for)|Блокируется до тех пор, пока связанная асинхронная операция не будет завершена или не истечет время, заданное `_Rel_time`.|
|[wait_until](#wait_until)|Блокируется до завершения связанной асинхронной операции или до тех пор, пока текущее время не превысит значение, заданное `_Abs_time`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Description|
|----------|-----------------|
|[operator std:: shared_future\<void >](#operator_shared_future)|Неявно преобразует объект `completion_future` в объект `std::shared_future`.|
|[оператор=](#operator_eq)|Копирует содержимое указанного объекта `completion_future` в этот объект.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`completion_future`

## <a name="requirements"></a>Требования

**Заголовок:** ампрт. h

**Пространство имен:** concurrency

## <a name="ctor"></a>completion_future

Инициализирует новый экземпляр класса `completion_future`.

### <a name="syntax"></a>Синтаксис

```cpp
completion_future();

completion_future(
    const completion_future& _Other );

completion_future(
    completion_future&& _Other );
```

### <a name="parameters"></a>Параметры

*_Other*<br/>
Объект `completion_future` для копирования или перемещения.

### <a name="overloads-list"></a>Список перегрузок

|Имя|Description|
|----------|-----------------|
|`completion_future();`|Инициализирует новый экземпляр класса `completion_future`|
|`completion_future(const completion_future& _Other);`|Инициализирует новый экземпляр класса `completion_future` путем копирования конструктора.|
|`completion_future(completion_future&& _Other);`|Инициализирует новый экземпляр класса `completion_future`, перемещая конструктор.|

## <a name="get"></a>Получить

Ожидает завершения связанной асинхронной операции. Создает хранимое исключение, если оно было обнаружено во время асинхронной операции.

### <a name="syntax"></a>Синтаксис

```cpp
void get() const;
```

## <a name="operator_shared_future"></a>operator std:: shared_future\<void >

Неявно преобразует объект `completion_future` в объект `std::shared_future`.

### <a name="syntax"></a>Синтаксис

```cpp
operator std::shared_future<void>() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект `std::shared_future`.

## <a name="operator_eq"></a>Оператор =

Копирует содержимое указанного объекта `completion_future` в этот объект.

### <a name="syntax"></a>Синтаксис

```cpp
completion_future&  operator= (const completion_future& _Other );
completion_future&  operator= (completion_future&& _Other );
```

### <a name="parameters"></a>Параметры

*_Other*<br/>
Объект, из которого выполняется копирование.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот объект `completion_future`.

## <a name="overloads-list"></a>Список перегрузок

|Имя|Description|
|----------|-----------------|
|`completion_future& operator=(const completion_future& _Other);`|Копирует содержимое указанного объекта `completion_future` в этот объект с помощью глубокого копирования.|
|`completion_future& operator=(completion_future&& _Other);`|Копирует содержимое указанного `completion_future` объекта в этот объект с помощью назначения перемещения.|

## <a name="then"></a>этого

Повязывает объект функции обратного вызова к `completion_future` объекту, который будет выполнен, когда связанная асинхронная операция завершает выполнение.

### <a name="syntax"></a>Синтаксис

```cpp
template <typename _Functor>
void then(const _Functor & _Func ) const;
```

### <a name="parameters"></a>Параметры

*_Functor*<br/>
Функтор обратного вызова.

*_Func*<br/>
Объект функции обратного вызова.

## <a name="to_task"></a>to_task

Возвращает объект `task`, соответствующий связанной асинхронной операции.

### <a name="syntax"></a>Синтаксис

```cpp
concurrency::task<void> to_task() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект `task`, соответствующий связанной асинхронной операции.

## <a name="valid"></a>допустимым

Получает логическое значение, которое указывает, связан ли объект с асинхронной операцией.

### <a name="syntax"></a>Синтаксис

```cpp
bool valid() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если объект связан с асинхронной операцией; в противном случае — **значение false**.

## <a name="wait"></a>ожидания

Блокируется до завершения связанной асинхронной операции.

### <a name="syntax"></a>Синтаксис

```cpp
void wait() const;
```

## <a name="wait_for"></a>wait_for

Блокируется до тех пор, пока не завершится связанная асинхронная операция или не истечет время, заданное `_Rel_time`.

### <a name="syntax"></a>Синтаксис

```cpp
template <
    class _Rep,
    class _Period
>
std::future_status::future_status wait_for(
    const std::chrono::duration< _Rep, _Period>& _Rel_time ) const;
```

### <a name="parameters"></a>Параметры

*_Rep*<br/>
Арифметический тип, представляющий количество тактов.

*_Period*<br/>
Отношение std::, представляющее количество секунд, прошедших за такт.

*_Rel_time*<br/>
Максимальное время ожидания завершения операции.

### <a name="return-value"></a>Возвращаемое значение

Возвращает:

- `std::future_status::deferred`, если связанная асинхронная операция не выполняется.

- `std::future_status::ready`, если связанная асинхронная операция завершена.

- `std::future_status::timeout` по истечении указанного периода времени.

## <a name="wait_until"></a>wait_until

Блокируется до завершения связанной асинхронной операции или до тех пор, пока текущее время не превысит значение, заданное `_Abs_time`.

### <a name="syntax"></a>Синтаксис

```cpp
template <
    class _Clock,
    class _Duration
>
std::future_status::future_status wait_until(
    const std::chrono::time_point< _Clock, _Duration>& _Abs_time ) const;
```

### <a name="parameters"></a>Параметры

*_Clock*<br/>
Часы, на которые измеряется этот момент времени.

*_Duration*<br/>
Интервал времени с начала эпохи `_Clock`, после которого функция истечет время ожидания.

*_Abs_time*<br/>
Момент времени, после которого функция истечет время ожидания.

### <a name="return-value"></a>Возвращаемое значение

Возвращает:

1. `std::future_status::deferred`, если связанная асинхронная операция не выполняется.

1. `std::future_status::ready`, если связанная асинхронная операция завершена.

1. `std::future_status::timeout`, если истек указанный период времени.

## <a name="dtor"></a>~ completion_future

Уничтожает объект `completion_future`.

### <a name="syntax"></a>Синтаксис

```cpp
~completion_future();
```

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
