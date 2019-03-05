---
title: Класс task_options (среда выполнения с параллелизмом)
ms.date: 11/04/2016
f1_keywords:
- ppltasks/concurrency::task_options
ms.assetid: f93d146b-70f7-46ec-8c2f-c33b8bb0af69
ms.openlocfilehash: c832ce759c556765fa412b2ef77333bc6612b8c3
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57265214"
---
# <a name="taskoptions-class-concurrency-runtime"></a>Класс task_options (среда выполнения с параллелизмом)

Представляет допустимые параметры для создания задачи

## <a name="syntax"></a>Синтаксис

```
class task_options;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[(среда выполнения с параллелизмом) конструктор task_options::task_options](#ctor)|Перегружен. Заданный по умолчанию список параметров создания задачи|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание:|
|----------|-----------------|
|[task_options::get_cancellation_token метод (среда выполнения с параллелизмом)](#get_cancellation_token)|Возвращает токен отмены|
|[task_options::get_continuation_context метод (среда выполнения с параллелизмом)](#get_continuation_context)|Возвращает контекст продолжения|
|[task_options::get_scheduler метод (среда выполнения с параллелизмом)](#get_scheduler)|Возвращает планировщик|
|[task_options::has_cancellation_token метод (среда выполнения с параллелизмом)](#has_cancellation_token)|Показывает, был ли определен токен отмены пользователем|
|[task_options::has_scheduler метод (среда выполнения с параллелизмом)](#has_scheduler)|Показывает, был ли определен планировщик n пользователем|
|[task_options::set_cancellation_token метод (среда выполнения с параллелизмом)](#set_cancellation_token)|Задает токен в параметрах|
|[task_options::set_continuation_context метод (среда выполнения с параллелизмом)](#set_continuation_context)|Задает контекст данного продолжения в параметрах|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`task_options`

## <a name="requirements"></a>Требования

**Заголовок:** ppltasks.h

**Пространство имен:** concurrency

##  <a name="get_cancellation_token"></a>  task_options::get_cancellation_token метод (среда выполнения с параллелизмом)

Возвращает токен отмены

```
cancellation_token get_cancellation_token() const;
```

### <a name="return-value"></a>Возвращаемое значение

##  <a name="get_continuation_context"></a>  task_options::get_continuation_context метод (среда выполнения с параллелизмом)

Возвращает контекст продолжения

```
task_continuation_context get_continuation_context() const;
```

### <a name="return-value"></a>Возвращаемое значение

##  <a name="get_scheduler"></a>  task_options::get_scheduler метод (среда выполнения с параллелизмом)

Возвращает планировщик

```
scheduler_ptr get_scheduler() const;
```

### <a name="return-value"></a>Возвращаемое значение

##  <a name="has_cancellation_token"></a>  task_options::has_cancellation_token метод (среда выполнения с параллелизмом)

Показывает, был ли определен токен отмены пользователем

```
bool has_cancellation_token() const;
```

### <a name="return-value"></a>Возвращаемое значение

##  <a name="has_scheduler"></a>  task_options::has_scheduler метод (среда выполнения с параллелизмом)

Показывает, был ли определен планировщик n пользователем

```
bool has_scheduler() const;
```

### <a name="return-value"></a>Возвращаемое значение

##  <a name="set_cancellation_token"></a>  task_options::set_cancellation_token метод (среда выполнения с параллелизмом)

Задает токен в параметрах

```
void set_cancellation_token(cancellation_token _Token);
```

### <a name="parameters"></a>Параметры

`_Token`

##  <a name="set_continuation_context"></a>  task_options::set_continuation_context метод (среда выполнения с параллелизмом)

Задает контекст данного продолжения в параметрах

```
void set_continuation_context(task_continuation_context _ContinuationContext);
```

### <a name="parameters"></a>Параметры

`_ContinuationContext`

##  <a name="ctor"></a>  (среда выполнения с параллелизмом) конструктор task_options::task_options

Заданный по умолчанию список параметров создания задачи

```
task_options();

task_options(
    cancellation_token _Token);

task_options(
    task_continuation_context _ContinuationContext);

task_options(
    cancellation_token _Token,
    task_continuation_context _ContinuationContext);

template<typename _SchedType>
task_options(
    std::shared_ptr<_SchedType> _Scheduler);

task_options(
    scheduler_interface& _Scheduler);

task_options(
    scheduler_ptr _Scheduler);

task_options(
    const task_options& _TaskOptions);
```

### <a name="parameters"></a>Параметры

`_SchedType`

`_Token`

`_ContinuationContext`

`_Scheduler`

`_TaskOptions`

## <a name="see-also"></a>См. также

[Пространство имен concurrency](concurrency-namespace.md)
