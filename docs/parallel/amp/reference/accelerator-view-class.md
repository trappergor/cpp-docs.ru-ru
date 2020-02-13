---
title: Класс accelerator_view
ms.date: 03/27/2019
f1_keywords:
- accelerator_view
- AMPRT/accelerator_view
- AMPRT/Concurrency::accelerator_view::accelerator_view
- AMPRT/Concurrency::accelerator_view::create_marker
- AMPRT/Concurrency::accelerator_view::flush
- AMPRT/Concurrency::accelerator_view::get_accelerator
- AMPRT/Concurrency::accelerator_view::get_is_auto_selection
- AMPRT/Concurrency::accelerator_view::get_is_debug
- AMPRT/Concurrency::accelerator_view::get_queuing_mode
- AMPRT/Concurrency::accelerator_view::get_version
- AMPRT/Concurrency::accelerator_view::wait
- AMPRT/Concurrency::accelerator_view::accelerator
- AMPRT/Concurrency::accelerator_view::is_auto_selection
- AMPRT/Concurrency::accelerator_view::is_debug
- AMPRT/Concurrency::accelerator_view::queuing_mode
- AMPRT/Concurrency::accelerator_view::version
helpviewer_keywords:
- accelerator_view class
ms.assetid: 9f298c21-bf62-46e0-88b8-01c5c78ef144
ms.openlocfilehash: 8990566fb3a700d61de324f725dea3ec00006d04
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77127180"
---
# <a name="accelerator_view-class"></a>Класс accelerator_view

Представляет абстракцию виртуального устройства в ускорителе C++ обработки данных amp.

## <a name="syntax"></a>Синтаксис

```cpp
class accelerator_view;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Конструктор accelerator_view](#ctor)|Инициализирует новый экземпляр класса `accelerator_view`.|
|[Деструктор ~ accelerator_view](#dtor)|Уничтожает объект `accelerator_view`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[create_marker](#create_marker)|Возвращает будущее, чтобы отследить завершение всех команд, отправленных на данный момент, в этот объект `accelerator_view`.|
|[flush](#flush)|Отправляет все ожидающие команды, поставленные в очередь на объект `accelerator_view`, в ускоритель для выполнения.|
|[get_accelerator](#get_accelerator)|Возвращает объект `accelerator` для объекта `accelerator_view`.|
|[get_is_auto_selection](#get_is_auto_selection)|Возвращает логическое значение, указывающее, будет ли среда выполнения автоматически выбирать соответствующее сочетание клавиш при передаче объекта `accelerator_view` в [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).|
|[get_is_debug](#get_is_debug)|Возвращает логическое значение, указывающее, включен ли для объекта `accelerator_view` слой отладки для расширенных отчетов об ошибках.|
|[get_queuing_mode](#get_queuing_mode)|Возвращает режим очереди для объекта `accelerator_view`.|
|[get_version](#get_version)|Возвращает версию `accelerator_view`.|
|[ожидания](#wait)|Ожидает завершения всех команд, отправленных в объект `accelerator_view`.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Description|
|----------|-----------------|
|[operator!=](#operator_neq)|Сравнивает этот объект `accelerator_view` с другим и возвращает **значение false** , если они одинаковы; в противном случае возвращает **значение true**.|
|[оператор=](#operator_eq)|Копирует содержимое указанного объекта `accelerator_view` в этот объект.|
|[operator==](#operator_eq_eq)|Сравнивает этот объект `accelerator_view` с другим и возвращает **значение true** , если они одинаковы; в противном случае возвращает **значение false**.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Description|
|----------|-----------------|
|[Accelerator](#accelerator)|Возвращает объект `accelerator` для объекта `accelerator_view`.|
|[is_auto_selection](#is_auto_selection)|Возвращает логическое значение, указывающее, будет ли среда выполнения автоматически выбирать соответствующее сочетание клавиш при передаче объекта `accelerator_view` в [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).|
|[is_debug](#is_debug)|Возвращает логическое значение, указывающее, включен ли для объекта `accelerator_view` слой отладки для расширенных отчетов об ошибках.|
|[queuing_mode](#queuing_mode)|Возвращает режим очереди для объекта `accelerator_view`.|
|[version](#version)|Возвращает версию ускорителя.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`accelerator_view`

### <a name="remarks"></a>Remarks

Объект `accelerator_view` представляет собой логическое изолированное представление ускорителя. Одно физическое устройство вычислений может иметь множество логических изолированных `accelerator_view` объектов. Каждый ускоритель имеет объект `accelerator_view` по умолчанию. Можно создать дополнительные `accelerator_view` объекты.

Физические устройства могут совместно использоваться несколькими клиентскими потоками. Клиентские потоки могут совместно использовать один и тот же объект `accelerator_view` ускорителя, или каждый клиент может взаимодействовать с устройством вычислений через независимые объекты `accelerator_view` для изоляции от других клиентских потоков.

Объект `accelerator_view` может иметь одно из двух [queuing_mode состояний перечисления](concurrency-namespace-enums-amp.md#queuing_mode) . Если режим очереди `immediate`, такие команды, как `copy` и `parallel_for_each`, отправляются соответствующему устройству ускорителя, как только они возвращаются вызывающему. Если режим очереди `deferred`, то такие команды помещаются в очередь команд, которая соответствует объекту `accelerator_view`. Команды на самом деле не отправляются на устройство, пока не будет вызван `flush()`.

## <a name="requirements"></a>Требования

**Заголовок:** ампрт. h

**Пространство имен** : Concurrency

## <a name="accelerator"></a>Accelerator

Возвращает объект ускорителя для объекта accelerator_view.

### <a name="syntax"></a>Синтаксис

```cpp
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;
```

## <a name="ctor"></a>accelerator_view

Инициализирует новый экземпляр класса accelerator_view путем копирования существующего объекта `accelerator_view`.

### <a name="syntax"></a>Синтаксис

```cpp
accelerator_view( const accelerator_view & other );
```

### <a name="parameters"></a>Параметры

*other*<br/>
Копируемый объект `accelerator_view`.

## <a name="create_marker"></a>create_marker

Возвращает будущее, чтобы отследить завершение всех команд, отправленных на данный момент, в этот объект `accelerator_view`.

### <a name="syntax"></a>Синтаксис

```cpp
concurrency::completion_future create_marker();
```

### <a name="return-value"></a>Возвращаемое значение

Будущее, чтобы отследить завершение всех команд, отправленных на данный момент, в этот объект `accelerator_view`.

## <a name="flush"></a>flush

Отправляет все ожидающие команды, поставленные в очередь на объект accelerator_view, в ускоритель для выполнения.

### <a name="syntax"></a>Синтаксис

```cpp
void flush();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает `void`.

## <a name="get_accelerator"></a>get_accelerator

Возвращает объект ускорителя для объекта accelerator_view.

### <a name="syntax"></a>Синтаксис

```cpp
accelerator get_accelerator() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект ускорителя для объекта accelerator_view.

## <a name="get_is_auto_selection"></a>get_is_auto_selection

Возвращает логическое значение, указывающее, будет ли среда выполнения автоматически выбирать соответствующее сочетание клавиш при передаче accelerator_view в [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).

### <a name="syntax"></a>Синтаксис

```cpp
bool get_is_auto_selection() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если среда выполнения будет автоматически выбирать соответствующее сочетание клавиш; в противном случае — **значение false**.

## <a name="get_is_debug"></a>get_is_debug

Возвращает логическое значение, указывающее, включен ли для объекта accelerator_view слой отладки для расширенных отчетов об ошибках.

### <a name="syntax"></a>Синтаксис

```cpp
bool get_is_debug() const;
```

### <a name="return-value"></a>Возвращаемое значение

Логическое значение, указывающее, включен ли для объекта `accelerator_view` слой отладки для расширенных отчетов об ошибках.

## <a name="get_queuing_mode"></a>get_queuing_mode

Возвращает режим очереди для объекта accelerator_view.

### <a name="syntax"></a>Синтаксис

```cpp
queuing_mode get_queuing_mode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Режим очереди для объекта `accelerator_view`.

## <a name="get_version"></a>get_version

Возвращает версию accelerator_view.

### <a name="syntax"></a>Синтаксис

```cpp
unsigned int get_version() const;
```

### <a name="return-value"></a>Возвращаемое значение

Версия объекта `accelerator_view`.

## <a name="is_auto_selection"></a>is_auto_selection

Возвращает логическое значение, указывающее, будет ли среда выполнения автоматически выбирать соответствующее сочетание клавиш при передаче accelerator_view в [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).

### <a name="syntax"></a>Синтаксис

```cpp
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;
```

## <a name="is_debug"></a>is_debug

Получает логическое значение, указывающее, имеет ли объект accelerator_view уровень отладки, позволяющий формировать расширенные отчеты об ошибках.

### <a name="syntax"></a>Синтаксис

```cpp
__declspec(property(get= get_is_debug)) bool is_debug;
```

## <a name="operator_neq"></a>operator! =

Сравнивает этот объект accelerator_view с другим и возвращает **значение false** , если они одинаковы; в противном случае возвращает **значение true**.

### <a name="syntax"></a>Синтаксис

```cpp
bool operator!= ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>Параметры

*other*<br/>
Объект `accelerator_view` для сравнения с данным объектом.

### <a name="return-value"></a>Возвращаемое значение

**значение false** , если два объекта одинаковы; в противном случае — **значение true**.

## <a name="operator_eq"></a>Оператор =

Копирует содержимое указанного объекта accelerator_view в этот объект.

### <a name="syntax"></a>Синтаксис

```cpp
accelerator_view & operator= ( const accelerator_view & other );
```

### <a name="parameters"></a>Параметры

*other*<br/>
Объект `accelerator_view`, из которого производится копирование.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на измененный объект `accelerator_view`.

## <a name="operator_eq_eq"></a>Оператор = =

Сравнивает этот объект accelerator_view с другим и возвращает **значение true** , если они одинаковы; в противном случае возвращает **значение false**.

### <a name="syntax"></a>Синтаксис

```cpp
bool operator== ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>Параметры

*other*<br/>
Объект `accelerator_view` для сравнения с данным объектом.

### <a name="return-value"></a>Возвращаемое значение

**значение true** , если два объекта одинаковы; в противном случае — **значение false**.

## <a name="queuing_mode"></a>queuing_mode

Возвращает режим очереди для объекта accelerator_view.

### <a name="syntax"></a>Синтаксис

```cpp
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;
```

## <a name="version"></a>version

Возвращает версию accelerator_view.

### <a name="syntax"></a>Синтаксис

```cpp
__declspec(property(get= get_version)) unsigned int version;
```

## <a name="wait"></a>wait

Ожидает завершения всех команд, отправленных в объект accelerator_view.

### <a name="syntax"></a>Синтаксис

```cpp
void wait();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает `void`.

### <a name="remarks"></a>Remarks

Если [queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) `immediate`, этот метод немедленно возвращает значение без блокировки.

## <a name="dtor"></a>~ accelerator_view

Уничтожает объект accelerator_view.

### <a name="syntax"></a>Синтаксис

```cpp
~accelerator_view();
```

## <a name="see-also"></a>См. также раздел

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
