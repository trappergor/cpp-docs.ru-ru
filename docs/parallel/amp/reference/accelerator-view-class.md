---
title: Класс accelerator_view | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- accelerator_view
- AMPRT/accelerator_view
- AMPRT/Concurrency::accelerator_view:accelerator_view
- AMPRT/Concurrency::accelerator_view:create_marker
- AMPRT/Concurrency::accelerator_view:flush
- AMPRT/Concurrency::accelerator_view:get_accelerator
- AMPRT/Concurrency::accelerator_view:get_is_auto_selection
- AMPRT/Concurrency::accelerator_view:get_is_debug
- AMPRT/Concurrency::accelerator_view:get_queuing_mode
- AMPRT/Concurrency::accelerator_view:get_version
- AMPRT/Concurrency::accelerator_view:wait
- AMPRT/Concurrency::accelerator_view:accelerator
- AMPRT/Concurrency::accelerator_view:is_auto_selection
- AMPRT/Concurrency::accelerator_view:is_debug
- AMPRT/Concurrency::accelerator_view:queuing_mode
- AMPRT/Concurrency::accelerator_view:version
dev_langs:
- C++
helpviewer_keywords:
- accelerator_view class
ms.assetid: 9f298c21-bf62-46e0-88b8-01c5c78ef144
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 30eb0befda4d439bf4153d7c6726c982d3bf19ae
ms.sourcegitcommit: 8480f16893f09911f08a58caf684405404f7ac8e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/12/2018
ms.locfileid: "49163339"
---
# <a name="acceleratorview-class"></a>Класс accelerator_view

Представляет абстракцию виртуального устройства на ускорителе с параллельными данными C++ AMP.

### <a name="syntax"></a>Синтаксис

```
class accelerator_view;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[accelerator_view, конструктор](#ctor)|Инициализирует новый экземпляр класса `accelerator_view`.|
|[~ accelerator_view, деструктор](#dtor)|Уничтожает `accelerator_view` объекта.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[create_marker](#create_marker)|Возвращает фьючерс для отслеживания выполнения всех команд, отправленных до сих данному `accelerator_view` объекта.|
|[flush](#flush)|Отправляет все команды, ожидающие в очереди на `accelerator_view` объект для выполнения на ускорителе.|
|[get_accelerator](#get_accelerator)|Возвращает объект `accelerator` для объекта `accelerator_view`.|
|[get_is_auto_selection](#get_is_auto_selection)|Возвращает логическое значение, указывающее, будет ли среда выполнения автоматически выбирать соответствующий ускоритель при `accelerator_view` объект передается [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).|
|[get_is_debug](#get_is_debug)|Возвращает логическое значение, указывающее, является ли `accelerator_view` объект имеет уровень DEBUG для расширенных отчетов об ошибках.|
|[get_queuing_mode](#get_queuing_mode)|Возвращает режим организации очереди для `accelerator_view` объекта.|
|[get_version](#get_version)|Возвращает версию `accelerator_view`.|
|[wait](#wait)|Ожидает в течение всех команд, отправленных `accelerator_view` объекта до конца.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Описание|
|----------|-----------------|
|[operator!=](#operator_neq)|Сравнивает этот `accelerator_view` объект с другим и возвращает **false** если они совпадают; в противном случае возвращает **true**.|
|[оператор=](#operator_eq)|Копирует содержимое указанного объекта `accelerator_view` в данный объект.|
|[operator==](#operator_eq_eq)|Сравнивает этот `accelerator_view` объект с другим и возвращает **true** если они совпадают; в противном случае возвращает **false**.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[сочетаний клавиш](#accelerator)|Возвращает объект `accelerator` для объекта `accelerator_view`.|
|[is_auto_selection](#is_auto_selection)|Возвращает логическое значение, указывающее, будет ли среда выполнения автоматически выбирать соответствующий ускоритель при `accelerator_view` объект передается [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).|
|[is_debug](#is_debug)|Возвращает логическое значение, указывающее, является ли `accelerator_view` объект имеет уровень DEBUG для расширенных отчетов об ошибках.|
|[queuing_mode](#queuing_mode)|Получает режим организации очереди для `accelerator_view` объекта.|
|[version](#version)|Получает версию ускорителя.|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`accelerator_view`

### <a name="remarks"></a>Примечания

`accelerator_view` Представляет логическое изолированное представление ускорителя. Одно физическое вычислительное устройство может иметь несколько логических изолированных `accelerator_view` объектов. Каждый ускоритель имеет значение по умолчанию `accelerator_view` объекта. Дополнительные `accelerator_view` объекты могут создаваться.

Физические устройства могут быть совместно использованы несколькими клиентскими потоками. Клиентские потоки могут совместно использовать же `accelerator_view` объект ускорителя, либо каждый клиент может взаимодействовать с вычислительным устройством через независимый `accelerator_view` объект для изоляции от других клиентских потоков.

`accelerator_view` Объект может иметь один из двух [перечисление queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) состояний. Если режим организации очереди — `immediate`, команды, такие как `copy` и `parallel_for_each` направляются в соответствующий ускоритель, как только они возвращаются вызывающему объекту. Если режим организации очереди — `deferred`, такие команды скапливаются в очереди команд, соответствующий `accelerator_view` объекта. Команды не отправляются фактически на устройстве до `flush()` вызывается.

## <a name="requirements"></a>Требования

**Заголовок:** amprt.h

**Пространство имен** : Concurrency

## <a name="accelerator"></a> сочетаний клавиш

Получает объект сочетаний клавиш для объекта accelerator_view.

### <a name="syntax"></a>Синтаксис

```
__declspec(property(get= get_accelerator)) Concurrency::accelerator accelerator;
```

## <a name="ctor"></a> accelerator_view

Инициализирует новый экземпляр класса accelerator_view путем копирования существующего `accelerator_view` объекта.

### <a name="syntax"></a>Синтаксис

```
accelerator_view( const accelerator_view & _Other );
```

### <a name="parameters"></a>Параметры

*_Другое*<br/>
`accelerator_view` Копируемый объект.

## <a name="accelerator_view__create_marker"></a> create_marker

Возвращает фьючерс для отслеживания выполнения всех команд, отправленных до сих данному `accelerator_view` объекта.

### <a name="syntax"></a>Синтаксис

```
concurrency::completion_future create_marker();
```

### <a name="return-value"></a>Возвращаемое значение

Объект фьючерса для отслеживания выполнения всех команд, отправленных до сих к этому `accelerator_view` объекта.

## <a name="flush"></a> Очистить

Отправляет все ожидающие выполнения команды в очереди на объект accelerator_view, который для выполнения на ускорителе.

### <a name="syntax"></a>Синтаксис

```
void flush();
```

### <a name="return-value"></a>Возвращаемое значение

Возвращает `void`.

## <a name="accelerator_view__get_accelerator"></a> get_accelerator

Возвращает объект ускорителя, объекта accelerator_view.
### <a name="syntax"></a>Синтаксис

```
accelerator get_accelerator() const;
```
### <a name="return-value"></a>Возвращаемое значение

Объект ускорителя, объекта accelerator_view.

## <a name="accelerator_view__get_is_auto_selection"></a> get_is_auto_selection

Возвращает логическое значение, указывающее, будет ли среда выполнения автоматически выбирать соответствующий ускоритель при передаче accelerator_view [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).

### <a name="syntax"></a>Синтаксис

```
bool get_is_auto_selection() const;
```

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если среда выполнения будет автоматически выбирать соответствующий ускоритель; в противном случае **false**.

## <a name="accelerator_view__get_is_debug"></a> get_is_debug

Возвращает логическое значение, указывающее, имеет ли объект accelerator_view уровень DEBUG для расширенных отчетов об ошибках.

### <a name="syntax"></a>Синтаксис

```
bool get_is_debug() const;
```

### <a name="return-value"></a>Возвращаемое значение

Логическое значение, указывающее, является ли `accelerator_view` объект имеет уровень DEBUG для расширенных отчетов об ошибках.

## <a name="accelerator_view__get_queuing_mode"></a> get_queuing_mode

Возвращает режим организации очереди, объекта accelerator_view.

### <a name="syntax"></a>Синтаксис

```
queuing_mode get_queuing_mode() const;
```

### <a name="return-value"></a>Возвращаемое значение

Режим организации очереди для `accelerator_view` объекта.

## <a name="accelerator_view__get_version"></a> get_version

Возвращает версию accelerator_view.

### <a name="syntax"></a>Синтаксис

```
unsigned int get_version() const;
```

### <a name="return-value"></a>Возвращаемое значение

Версия `accelerator_view`.

## <a name="accelerator_view__is_auto_selection"></a> is_auto_selection

Возвращает логическое значение, указывающее, будет ли среда выполнения автоматически выбирать соответствующий ускоритель при передаче accelerator_view [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each).

### <a name="syntax"></a>Синтаксис

```
__declspec(property(get= get_is_auto_selection)) bool is_auto_selection;
```

## <a name="accelerator_view__is_debug"></a> is_debug

Возвращает логическое значение, указывающее, имеет ли объект accelerator_view уровень DEBUG для расширенных отчетов об ошибках.

### <a name="syntax"></a>Синтаксис

```
__declspec(property(get= get_is_debug)) bool is_debug;
```

## <a name="accelerator_view__operator_neq"></a> оператор! =

Сравнивает данный объект accelerator_view, с другим и возвращает **false** если они совпадают; в противном случае возвращает **true**.

### <a name="syntax"></a>Синтаксис

```
bool operator!= (    const accelerator_view & _Other ) const;
```

### <a name="parameters"></a>Параметры

*_Другое*<br/>
`accelerator_view` Объект, сравниваемый с данным элементом.

### <a name="return-value"></a>Возвращаемое значение

**false** Если два объекта одинаковы; в противном случае **true**.

## <a name="accelerator_view__operator_eq"></a> оператор =

Копирует содержимое указанного accelerator_view объекта в другой.

### <a name="syntax"></a>Синтаксис

```
accelerator_view & operator= (    const accelerator_view & _Other );
```

### <a name="parameters"></a>Параметры

*_Другое*<br/>
`accelerator_view` Для копирования.

### <a name="return-value"></a>Возвращаемое значение

Ссылку на измененный `accelerator_view` объекта.

## <a name="accelerator_view__operator_eq_eq"></a> оператор ==

Сравнивает данный объект accelerator_view, с другим и возвращает **true** если они совпадают; в противном случае возвращает **false**.

### <a name="syntax"></a>Синтаксис

```
bool operator= = (    const accelerator_view & _Other ) const;
```

### <a name="parameters"></a>Параметры

*_Другое*<br/>
`accelerator_view` Объект, сравниваемый с данным элементом.

### <a name="return-value"></a>Возвращаемое значение

**значение true,** Если два объекта одинаковы; в противном случае **false**.

## <a name="accelerator_view__queuing_mode"></a> queuing_mode

Получает режим организации очереди для объекта accelerator_view.

### <a name="syntax"></a>Синтаксис

```
__declspec(property(get= get_queuing_mode)) Concurrency::queuing_mode queuing_mode;
```

## <a name="accelerator_view__version"></a> Версия

Получает версию accelerator_view.

### <a name="syntax"></a>Синтаксис

```
__declspec(property(get= get_version)) unsigned int version;
```

## <a name="accelerator_view__wait"></a> Подождите

Ожидает в течение всех команд, отправленных в объект accelerator_view, Готово.

### <a name="syntax"></a>Синтаксис

```
void wait();
```

#### <a name="return-value"></a>Возвращаемое значение

Возвращает `void`.

#### <a name="remarks"></a>Примечания

Если [queuing_mode](concurrency-namespace-enums-amp.md#queuing_mode) является `immediate`, этот метод завершается сразу без блокировки.

##  <a name="dtor"></a> ~ accelerator_view

Уничтожает объект accelerator_view.

#### <a name="syntax"></a>Синтаксис

```
~accelerator_view();
```

### <a name="return-value"></a>Возвращаемое значение

## <a name="see-also"></a>См. также

[Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
