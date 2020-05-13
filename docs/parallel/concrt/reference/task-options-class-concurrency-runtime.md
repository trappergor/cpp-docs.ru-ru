---
title: Класс task_options (среда выполнения с параллелизмом)
ms.date: 11/04/2016
f1_keywords:
- ppltasks/concurrency::task_options
ms.assetid: f93d146b-70f7-46ec-8c2f-c33b8bb0af69
ms.openlocfilehash: e79dd7979b587ae807c8984a04b79be362b03758
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81368596"
---
# <a name="task_options-class-concurrency-runtime"></a>Класс task_options (среда выполнения с параллелизмом)

Представляет допустимые параметры для создания задачи

## <a name="syntax"></a>Синтаксис

```cpp
class task_options;
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[Конструктор task_options::task_options (среда выполнения с параллелизмом)](#ctor)|Перегружен. Заданный по умолчанию список параметров создания задачи|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[Метод task_options::get_cancellation_token (среда выполнения с параллелизмом)](#get_cancellation_token)|Возвращает токен отмены|
|[Метод task_options::get_continuation_context (среда выполнения с параллелизмом)](#get_continuation_context)|Возвращает контекст продолжения|
|[Метод task_options::get_scheduler (среда выполнения с параллелизмом)](#get_scheduler)|Возвращает планировщик|
|[Метод task_options::has_cancellation_token (среда выполнения с параллелизмом)](#has_cancellation_token)|Показывает, был ли определен токен отмены пользователем|
|[Метод task_options::has_scheduler (среда выполнения с параллелизмом)](#has_scheduler)|Показывает, был ли определен планировщик n пользователем|
|[Метод task_options::set_cancellation_token (среда выполнения с параллелизмом)](#set_cancellation_token)|Задает токен в параметрах|
|[Метод task_options::set_continuation_context (среда выполнения с параллелизмом)](#set_continuation_context)|Задает контекст данного продолжения в параметрах|

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`task_options`

## <a name="requirements"></a>Требования

**Заголовок:** ppltasks.h

**Название:** параллелизм

## <a name="task_optionsget_cancellation_token-method-concurrency-runtime"></a><a name="get_cancellation_token"></a>task_options:::get_cancellation_token метод (Курсна)

Возвращает токен отмены

```cpp
cancellation_token get_cancellation_token() const;
```

### <a name="return-value"></a>Возвращаемое значение

## <a name="task_optionsget_continuation_context-method-concurrency-runtime"></a><a name="get_continuation_context"></a>task_options::get_continuation_context метод (Время выполнения параллели)

Возвращает контекст продолжения

```cpp
task_continuation_context get_continuation_context() const;
```

### <a name="return-value"></a>Возвращаемое значение

## <a name="task_optionsget_scheduler-method-concurrency-runtime"></a><a name="get_scheduler"></a>task_options:::get_scheduler метод (Курсна)

Возвращает планировщик

```cpp
scheduler_ptr get_scheduler() const;
```

### <a name="return-value"></a>Возвращаемое значение

## <a name="task_optionshas_cancellation_token-method-concurrency-runtime"></a><a name="has_cancellation_token"></a>task_options::has_cancellation_token метод (Курсна)

Показывает, был ли определен токен отмены пользователем

```cpp
bool has_cancellation_token() const;
```

### <a name="return-value"></a>Возвращаемое значение

## <a name="task_optionshas_scheduler-method-concurrency-runtime"></a><a name="has_scheduler"></a>task_options::has_scheduler метод (Курсна)

Показывает, был ли определен планировщик n пользователем

```cpp
bool has_scheduler() const;
```

### <a name="return-value"></a>Возвращаемое значение

## <a name="task_optionsset_cancellation_token-method-concurrency-runtime"></a><a name="set_cancellation_token"></a>task_options::set_cancellation_token метод (Курсна runtime)

Задает токен в параметрах

```cpp
void set_cancellation_token(cancellation_token _Token);
```

### <a name="parameters"></a>Параметры

`_Token`

## <a name="task_optionsset_continuation_context-method-concurrency-runtime"></a><a name="set_continuation_context"></a>task_options::set_continuation_context метод (Время выполнения параллели)

Задает контекст данного продолжения в параметрах

```cpp
void set_continuation_context(task_continuation_context _ContinuationContext);
```

### <a name="parameters"></a>Параметры

`_ContinuationContext`

## <a name="task_optionstask_options-constructor-concurrency-runtime"></a><a name="ctor"></a>task_options::task_options Конструктор (Курсна)

Заданный по умолчанию список параметров создания задачи

```cpp
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

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)
