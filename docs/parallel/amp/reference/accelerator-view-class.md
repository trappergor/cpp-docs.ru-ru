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
ms.openlocfilehash: f3be8cc3ab9a0f36027cc38c88f026570d1fdb55
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81370893"
---
# <a name="accelerator_view-class"></a>Класс accelerator_view

Представляет собой виртуальную абстракцию устройства на параллельном ускорителе данных C'AMP.

## <a name="syntax"></a>Синтаксис

```cpp
class accelerator_view;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[accelerator_view конструктор](#ctor)|Инициализирует новый экземпляр класса `accelerator_view`.|
|[«accelerator_view деструктор](#dtor)|Уничтожает `accelerator_view` объект.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[create_marker](#create_marker)|Возвращает будущее для отслеживания завершения всех команд, `accelerator_view` представленных до сих пор этому объекту.|
|[flush](#flush)|Отправляет все ожидающие команды в `accelerator_view` очередь объекту на ускоритель для выполнения.|
|[get_accelerator](#get_accelerator)|Возвращает объект `accelerator` для объекта `accelerator_view`.|
|[get_is_auto_selection](#get_is_auto_selection)|Возвращает значение Boolean, которое указывает на то, автоматически ли время `accelerator_view` выполнения выберет соответствующий ускоритель при переносе объекта в [parallel_for_each.](concurrency-namespace-functions-amp.md#parallel_for_each)|
|[get_is_debug](#get_is_debug)|Возвращает значение Boolean, которое указывает, включен ли `accelerator_view` у объекта слой DEBUG для обширной отчетности об ошибках.|
|[get_queuing_mode](#get_queuing_mode)|Возвращает режим очереди для `accelerator_view` объекта.|
|[get_version](#get_version)|Возвращает версию `accelerator_view`.|
|[Подожди](#wait)|Ожидает завершения всех команд, `accelerator_view` представленных объекту.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[оператора!](#operator_neq)|Сравнивает `accelerator_view` этот объект с другим и возвращает **ложно,** если они одинаковы; в противном случае, **возвращается верно**.|
|[оператора](#operator_eq)|Копирует содержимое указанного `accelerator_view` объекта в этот.|
|[оператора](#operator_eq_eq)|Сравнивает `accelerator_view` этот объект с другим и **возвращается верно,** если они одинаковы; в противном случае, возвращает **ложные**.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[Ускоритель](#accelerator)|Возвращает объект `accelerator` для объекта `accelerator_view`.|
|[is_auto_selection](#is_auto_selection)|Получает значение Boolean, которое указывает на то, автоматически ли время `accelerator_view` выполнения выберет соответствующий ускоритель при перевале объекта в [parallel_for_each.](concurrency-namespace-functions-amp.md#parallel_for_each)|
|[is_debug](#is_debug)|Получает значение Boolean, которое указывает, включен ли `accelerator_view` у объекта слой DEBUG для обширной отчетности об ошибках.|
|[queuing_mode](#queuing_mode)|Получает режим очередей для `accelerator_view` объекта.|
|[version](#version)|Получает версию ускорителя.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`accelerator_view`

### <a name="remarks"></a>Remarks

Объект `accelerator_view` представляет собой логический, изолированный вид ускорителя. Одно физическое вычислительное устройство может `accelerator_view` иметь много логических, изолированных объектов. Каждый ускоритель имеет объект `accelerator_view` по умолчанию. Могут `accelerator_view` быть созданы дополнительные объекты.

Физические устройства могут быть общими между многими потоками клиента. Клиентские потоки могут совместно `accelerator_view` использовать один и тот же объект ускорителя, или каждый `accelerator_view` клиент может общаться с вычислительным устройством через независимый объект для изоляции от других потоков клиента.

Объект `accelerator_view` может иметь одно из двух queuing_mode состояния [enumeration.](concurrency-namespace-enums-amp.md#queuing_mode) Если режим очереди, `immediate`команды, `copy` как `parallel_for_each` и отправляются на соответствующий ускоритель устройства, как только они возвращаются к вызывающему. При наличии режима `deferred`очереди такие команды стоят в очереди в командной очереди, соответствующей объекту. `accelerator_view` Команды на самом деле не `flush()` отправляются на устройство до тех пор, пока не будет вызвано.

## <a name="requirements"></a>Требования

**Заголовок:** amprt.h

**Пространство имен** : Concurrency

## <a name="accelerator"></a><a name="accelerator"></a>Ускоритель

Получает объект ускорителя для accelerator_view объекта.

### <a name="syntax"></a>Синтаксис

```cpp
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;
```

## <a name="accelerator_view"></a><a name="ctor"></a>Accelerator_view

Инициализирует новый экземпляр класса accelerator_view, копируя существующий `accelerator_view` объект.

### <a name="syntax"></a>Синтаксис

```cpp
accelerator_view( const accelerator_view & other );
```

### <a name="parameters"></a>Параметры

*Других*<br/>
Копируемый объект `accelerator_view`.

## <a name="create_marker"></a><a name="create_marker"></a>create_marker

Возвращает будущее для отслеживания завершения всех команд, `accelerator_view` представленных до сих пор этому объекту.

### <a name="syntax"></a>Синтаксис

```cpp
concurrency::completion_future create_marker();
```

### <a name="return-value"></a>Возвращаемое значение

Будущее для отслеживания завершения всех команд, `accelerator_view` представленных до сих пор на этот объект.

## <a name="flush"></a>flush

Отправляет все ожидающие команды в очередь на accelerator_view объект к ускорителю для выполнения.

### <a name="syntax"></a>Синтаксис

```cpp
void flush();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает `void`.

## <a name="get_accelerator"></a><a name="get_accelerator"></a>get_accelerator

Возвращает объект ускорителя для объекта accelerator_view.

### <a name="syntax"></a>Синтаксис

```cpp
accelerator get_accelerator() const;
```

### <a name="return-value"></a>Возвращаемое значение

Объект ускорителя для accelerator_view объекта.

## <a name="get_is_auto_selection"></a><a name="get_is_auto_selection"></a>get_is_auto_selection

Возвращает значение Boolean, которое указывает на то, автоматически ли время выполнения выберет соответствующий ускоритель при accelerator_view передается [parallel_for_each.](concurrency-namespace-functions-amp.md#parallel_for_each)

### <a name="syntax"></a>Синтаксис

```cpp
bool get_is_auto_selection() const;
```

### <a name="return-value"></a>Возвращаемое значение

**верно,** если время выполнения автоматически выберет соответствующий ускоритель; в противном случае, **ложные**.

## <a name="get_is_debug"></a><a name="get_is_debug"></a>get_is_debug

Возвращает значение Boolean, которое указывает, имеет ли accelerator_view объект слой DEBUG для обширной отчетности об ошибках.

### <a name="syntax"></a>Синтаксис

```cpp
bool get_is_debug() const;
```

### <a name="return-value"></a>Возвращаемое значение

Значение Boolean, которое `accelerator_view` указывает, включен ли у объекта слой DEBUG для обширной отчетности об ошибках.

## <a name="get_queuing_mode"></a><a name="get_queuing_mode"></a>get_queuing_mode

Возвращает режим очереди для объекта accelerator_view.

### <a name="syntax"></a>Синтаксис

```cpp
queuing_mode get_queuing_mode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Режим очереди для `accelerator_view` объекта.

## <a name="get_version"></a><a name="get_version"></a>get_version

Возвращает версию accelerator_view.

### <a name="syntax"></a>Синтаксис

```cpp
unsigned int get_version() const;
```

### <a name="return-value"></a>Возвращаемое значение

Версия объекта `accelerator_view`.

## <a name="is_auto_selection"></a><a name="is_auto_selection"></a>is_auto_selection

Получает значение Boolean, которое указывает на то, автоматически ли время выполнения выберет соответствующий ускоритель при accelerator_view передается [parallel_for_each.](concurrency-namespace-functions-amp.md#parallel_for_each)

### <a name="syntax"></a>Синтаксис

```cpp
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;
```

## <a name="is_debug"></a><a name="is_debug"></a>is_debug

Получает логическое значение, указывающее, имеет ли объект accelerator_view уровень отладки, позволяющий формировать расширенные отчеты об ошибках.

### <a name="syntax"></a>Синтаксис

```cpp
__declspec(property(get= get_is_debug)) bool is_debug;
```

## <a name="operator"></a><a name="operator_neq"></a>оператора!

Сравнивает этот accelerator_view объект с другим и возвращает **ложно,** если они одинаковы; в противном случае, **возвращается верно**.

### <a name="syntax"></a>Синтаксис

```cpp
bool operator!= ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>Параметры

*Других*<br/>
Объект `accelerator_view` для сравнения с этим.

### <a name="return-value"></a>Возвращаемое значение

**ложные,** если эти два объекта одинаковы; в противном случае, **правда**.

## <a name="operator"></a><a name="operator_eq"></a>оператора

Копирует содержимое указанного accelerator_view объект в этот объект.

### <a name="syntax"></a>Синтаксис

```cpp
accelerator_view & operator= ( const accelerator_view & other );
```

### <a name="parameters"></a>Параметры

*Других*<br/>
Объект `accelerator_view` для копирования.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на измененный `accelerator_view` объект.

## <a name="operator"></a><a name="operator_eq_eq"></a>оператора

Сравнивает этот accelerator_view объект с другим и **возвращается верно,** если они одинаковы; в противном случае, возвращает **ложные**.

### <a name="syntax"></a>Синтаксис

```cpp
bool operator== ( const accelerator_view & other ) const;
```

### <a name="parameters"></a>Параметры

*Других*<br/>
Объект `accelerator_view` для сравнения с этим.

### <a name="return-value"></a>Возвращаемое значение

**верно,** если два объекта одинаковы; в противном случае, **ложные**.

## <a name="queuing_mode"></a><a name="queuing_mode"></a>queuing_mode

Получает режим очередей для объекта accelerator_view.

### <a name="syntax"></a>Синтаксис

```cpp
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;
```

## <a name="version"></a>version

Получает версию accelerator_view.

### <a name="syntax"></a>Синтаксис

```cpp
__declspec(property(get= get_version)) unsigned int version;
```

## <a name="wait"></a>wait

Ожидает сябо всех команд, представленных объекту accelerator_view до завершения.

### <a name="syntax"></a>Синтаксис

```cpp
void wait();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает `void`.

### <a name="remarks"></a>Remarks

Если [queuing_mode,](concurrency-namespace-enums-amp.md#queuing_mode) `immediate`этот метод возвращается немедленно без блокировки.

## <a name="accelerator_view"></a><a name="dtor"></a>(accelerator_view

Уничтожает accelerator_view объект.

### <a name="syntax"></a>Синтаксис

```cpp
~accelerator_view();
```

## <a name="see-also"></a>См. также раздел

[Пространство имен параллелизма (КЗ АМП)](concurrency-namespace-cpp-amp.md)
