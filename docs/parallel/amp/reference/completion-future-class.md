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
ms.openlocfilehash: 663122c2d8cd430e921773e75dfd7975e4a41516
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57272923"
---
# <a name="completionfuture-class"></a>Класс completion_future

Представляет фьючерс, соответствующей асинхронной операции C++ AMP.

### <a name="syntax"></a>Синтаксис

```
class completion_future;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор completion_future](#ctor)|Инициализирует новый экземпляр класса `completion_future`.|
|[~ completion_future деструктор](#dtor)|Уничтожает `completion_future` объекта.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[get](#get)|Ожидает, пока не завершится соответствующая асинхронная операция.|
|[Затем](#then)|Добавляет объект функции обратного вызова для `completion_future` объект для выполнения после соответствующая асинхронная операция завершения выполнения.|
|[to_task](#to_task)|Возвращает `task` объект, соответствующий связанной асинхронной операции.|
|[допустимый](#valid)|Возвращает логическое значение, указывающее, связан ли объект с асинхронной операцией.|
|[wait](#wait)|Блокируется, пока не завершится соответствующая асинхронная операция.|
|[wait_for](#wait_for)|Блоки, пока не завершится соответствующая асинхронная операция или времени, заданного параметром `_Rel_time` истечет.|
|[wait_until](#wait_until)|Блокирует пока не завершится соответствующая асинхронная операция, или до текущего времени превышает значение, заданное параметром `_Abs_time`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание:|
|----------|-----------------|
|[оператор std::shared_future\<void >](#operator_shared_future)|Неявно преобразует `completion_future` объект `std::shared_future` объекта.|
|[оператор=](#operator_eq)|Копирует содержимое указанного объекта `completion_future` в данный объект.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`completion_future`

## <a name="requirements"></a>Требования

**Заголовок:** amprt.h

**Пространство имен:** concurrency

## <a name="ctor"></a> completion_future

Инициализирует новый экземпляр класса `completion_future`.

### <a name="syntax"></a>Синтаксис

```
completion_future();

completion_future(
    const completion_future& _Other );

completion_future(
    completion_future&& _Other );
```

### <a name="parameters"></a>Параметры

*_Другое*<br/>
`completion_future` Объект для копирования или перемещения.

### <a name="overloads-list"></a>Список перегрузок

|Имя|Описание:|
|----------|-----------------|
|`completion_future();`|Инициализирует новый экземпляр класса `completion_future` класса|
|`completion_future(const completion_future& _Other);`|Инициализирует новый экземпляр класса `completion_future` путем копирования конструктором.|
|`completion_future(completion_future&& _Other);`|Инициализирует новый экземпляр класса `completion_future` класса путем перемещения конструктора.|

## <a name="get"></a> Получить

Ожидает, пока не завершится соответствующая асинхронная операция. Хранимые исключение вызывается в том случае, если один была обнаружена во время асинхронной операции.

### <a name="syntax"></a>Синтаксис

```
void get() const;
```

## <a name="operator_shared_future"></a> operator std::shared_future<void>

Неявно преобразует `completion_future` объект `std::shared_future` объекта.

### <a name="syntax"></a>Синтаксис

```
operator std::shared_future<void>() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект `std::shared_future`.

## <a name="operator_eq"></a> оператор =

Копирует содержимое указанного объекта `completion_future` в данный объект.

### <a name="syntax"></a>Синтаксис

```
completion_future&  operator= (const completion_future& _Other );
completion_future&  operator= (completion_future&& _Other );
```

### <a name="parameters"></a>Параметры

*_Другое*<br/>
Копируемый объект.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на этот `completion_future` объекта.

## <a name="overloads-list"></a>Список перегрузок

|Имя|Описание:|
|----------|-----------------|
|`completion_future& operator=(const completion_future& _Other);`|Копирует содержимое указанного объекта `completion_future` объекта в данный помощи глубокого копирования.|
|`completion_future& operator=(completion_future&& _Other);`|Копирует содержимое указанного объекта `completion_future` объекта в данный помощи присваивания с перемещением.|

## <a name="then"></a> Затем

Добавляет объект функции обратного вызова для `completion_future` объект для выполнения после соответствующая асинхронная операция завершения выполнения.

### <a name="syntax"></a>Синтаксис

```
template <typename _Functor>
void then(const _Functor & _Func ) const;
```

### <a name="parameters"></a>Параметры

*_Functor*<br/>
Функтор обратного вызова.

*_Func*<br/>
Объект функции обратного вызова.

## <a name="to_task"></a> to_task

Возвращает `task` объект, соответствующий связанной асинхронной операции.

### <a name="syntax"></a>Синтаксис

```
concurrency::task<void> to_task() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект `task` объект, соответствующий связанной асинхронной операции.

## <a name="valid"></a> допустимый

Получает логическое значение, которое указывает, связан ли объект с асинхронной операцией.

### <a name="syntax"></a>Синтаксис

```
bool valid() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если объект, связанный с асинхронной операцией, в противном случае — **false**.

## <a name="wait"></a> Подождите

Блокируется, пока не завершится соответствующая асинхронная операция.

### <a name="syntax"></a>Синтаксис

```
void wait() const;
```

## <a name="wait_for"></a> wait_for

Блоки, пока не завершится соответствующая асинхронная операция или времени, который задается параметром `_Rel_time` истечет.

### <a name="syntax"></a>Синтаксис

```
template <
    class _Rep,
    class _Period
>
std::future_status::future_status wait_for(
    const std::chrono::duration< _Rep, _Period>& _Rel_time ) const;
```

### <a name="parameters"></a>Параметры

*_Rep*<br/>
Арифметический тип, который представляет количество тактов.

*_Period*<br/>
Std::ratio, представляющий количество секунд, истекающих за такт.

*_Rel_time*<br/>
Максимальное время ожидания завершения операции.

### <a name="return-value"></a>Возвращаемое значение

Возвращает:

- `std::future_status::deferred` Если соответствующая асинхронная операция не выполняется.

- `std::future_status::ready` Если соответствующая асинхронная операция завершена.

- `std::future_status::timeout` Если указанный интервал времени.

## <a name="wait_until"></a> wait_until

Блокирует пока не завершится соответствующая асинхронная операция, или до текущего времени превышает значение, заданное параметром `_Abs_time`.

### <a name="syntax"></a>Синтаксис

```
template <
    class _Clock,
    class _Duration
>
std::future_status::future_status wait_until(
    const std::chrono::time_point< _Clock, _Duration>& _Abs_time ) const;
```

### <a name="parameters"></a>Параметры

*_Clock*<br/>
Часы, на котором этот период времени измеряется.

*_Duration*<br/>
Интервал времени с момента запуска `_Clock`элемента эпохи, после которого истекает функция.

*_Abs_time*<br/>
Момент времени, после чего она будет блокирована по времени.

### <a name="return-value"></a>Возвращаемое значение

Возвращает:

1. `std::future_status::deferred` Если соответствующая асинхронная операция не выполняется.

1. `std::future_status::ready` Если соответствующая асинхронная операция завершена.

1. `std::future_status::timeout` Если заданный период времени истек.

## <a name="dtor"></a> ~completion_future

Уничтожает `completion_future` объекта.

### <a name="syntax"></a>Синтаксис

```
~completion_future();
```

## <a name="see-also"></a>См. также

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
