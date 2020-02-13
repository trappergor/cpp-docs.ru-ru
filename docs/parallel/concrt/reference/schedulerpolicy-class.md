---
title: Класс SchedulerPolicy
ms.date: 11/04/2016
f1_keywords:
- SchedulerPolicy
- concrt/concurrency::SchedulerPolicy
- concrt/concurrency::SchedulerPolicy::SchedulerPolicy
- concrt/concurrency::SchedulerPolicy::GetPolicyValue
- concrt/concurrency::SchedulerPolicy::SetConcurrencyLimits
- concrt/concurrency::SchedulerPolicy::SetPolicyValue
helpviewer_keywords:
- SchedulerPolicy class
ms.assetid: bcebf51a-65f8-45a3-809b-d1ff93527dc4
ms.openlocfilehash: fed33c198502b75e824bcaf698227d283f4b85f9
ms.sourcegitcommit: a8ef52ff4a4944a1a257bdaba1a3331607fb8d0f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/11/2020
ms.locfileid: "77142751"
---
# <a name="schedulerpolicy-class"></a>Класс SchedulerPolicy

Класс `SchedulerPolicy` содержит набор пар «ключ — значение» по одной для каждого элемента политики, управляющего поведением экземпляра планировщика.

## <a name="syntax"></a>Синтаксис

```cpp
class SchedulerPolicy;
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[SchedulerPolicy](#ctor)|Перегружен. Конструирует новую политику планировщика и заполняет ее значениями для [ключей политик](concurrency-namespace-enums.md) , поддерживаемых планировщиками среда выполнения с параллелизмом и диспетчер ресурсов.|
|[Деструктор ~ SchedulerPolicy](#dtor)|Уничтожает политику планировщика.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[жетполицивалуе](#getpolicyvalue)|Возвращает значение ключа политики, передаваемое в качестве параметра `key`.|
|[сетконкурренцилимитс](#setconcurrencylimits)|Одновременно задает политики `MinConcurrency` и `MaxConcurrency` для объекта `SchedulerPolicy`.|
|[сетполицивалуе](#setpolicyvalue)|Задает значение ключа политики, предоставляемое в качестве параметра `key`, и возвращает старое значение.|

### <a name="public-operators"></a>Открытые операторы

|Имя|Description|
|----------|-----------------|
|[оператор=](#operator_eq)|Назначает политику планировщика из другой политики планировщика.|

## <a name="remarks"></a>Remarks

Дополнительные сведения о политиках, которые можно контролировать с помощью класса `SchedulerPolicy`, см. в разделе [полициелементкэй](concurrency-namespace-enums.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

`SchedulerPolicy`

## <a name="requirements"></a>Требования

**Заголовок:** ConcRT. h, concrtrm. h

**Пространство имен:** concurrency

## <a name="getpolicyvalue"></a>жетполицивалуе

Возвращает значение ключа политики, передаваемое в качестве параметра `key`.

```cpp
unsigned int GetPolicyValue(PolicyElementKey key) const;
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ политики для получения значения.

### <a name="return-value"></a>Возвращаемое значение

Если ключ, заданный параметром `key`, поддерживается, то значение политики для приведения ключа к `unsigned int`.

### <a name="remarks"></a>Remarks

Метод вызовет исключение [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md) для недопустимого ключа политики.

## <a name="operator_eq"></a>Оператор =

Назначает политику планировщика из другой политики планировщика.

```cpp
SchedulerPolicy& operator= (const SchedulerPolicy& _RhsPolicy);
```

### <a name="parameters"></a>Параметры

*_RhsPolicy*<br/>
Политика, назначаемая этой политике.

### <a name="return-value"></a>Возвращаемое значение

Ссылка на политику планировщика.

### <a name="remarks"></a>Remarks

Часто наиболее удобным способом для определения новой политики планировщика является копирование существующей политики и изменение ее методами `SetPolicyValue` или `SetConcurrencyLimits`.

## <a name="ctor"></a>SchedulerPolicy

Конструирует новую политику планировщика и заполняет ее значениями для [ключей политик](concurrency-namespace-enums.md) , поддерживаемых планировщиками среда выполнения с параллелизмом и диспетчер ресурсов.

```cpp
SchedulerPolicy();

SchedulerPolicy(
    size_t _PolicyKeyCount,
...);

SchedulerPolicy(
    const SchedulerPolicy& _SrcPolicy);
```

### <a name="parameters"></a>Параметры

*_PolicyKeyCount*<br/>
Число пар "ключ-значение", которые следуют за параметром `_PolicyKeyCount`.

*_SrcPolicy*<br/>
Исходная политика для копирования.

### <a name="remarks"></a>Remarks

Первый конструктор создает новую политику планировщика, где все политики будут инициализированы значениями по умолчанию.

Второй конструктор создает новую политику планировщика, в которой используется стиль инициализации с именованными параметрами. Значения после параметра `_PolicyKeyCount` предоставляются в виде пар "ключ-значение". Любой ключ политики, который не указан в этом конструкторе, будет иметь значение по умолчанию. Этот конструктор может вызывать исключения [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md), [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) или [invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md).

Третий конструктор является конструктором копии. Часто наиболее удобным способом для определения новой политики планировщика является копирование существующей политики и изменение ее методами `SetPolicyValue` или `SetConcurrencyLimits`.

## <a name="dtor"></a>~ SchedulerPolicy

Уничтожает политику планировщика.

```cpp
~SchedulerPolicy();
```

## <a name="setconcurrencylimits"></a>сетконкурренцилимитс

Одновременно задает политики `MinConcurrency` и `MaxConcurrency` для объекта `SchedulerPolicy`.

```cpp
void SetConcurrencyLimits(
    unsigned int _MinConcurrency,
    unsigned int _MaxConcurrency = MaxExecutionResources);
```

### <a name="parameters"></a>Параметры

*_MinConcurrency*<br/>
Значение ключа политики `MinConcurrency`.

*_MaxConcurrency*<br/>
Значение ключа политики `MaxConcurrency`.

### <a name="remarks"></a>Remarks

Метод вызовет исключение [invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md) , если значение, указанное для политики `MinConcurrency`, больше, чем указано для политики `MaxConcurrency`.

Метод также может создавать [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) для других недопустимых значений.

## <a name="setpolicyvalue"></a>сетполицивалуе

Задает значение ключа политики, предоставляемое в качестве параметра `key`, и возвращает старое значение.

```cpp
unsigned int SetPolicyValue(
    PolicyElementKey key,
    unsigned int value);
```

### <a name="parameters"></a>Параметры

*key*<br/>
Ключ политики для задания значения.

*value*<br/>
Значение, для которого необходимо задать ключ политики.

### <a name="return-value"></a>Возвращаемое значение

Если ключ, заданный параметром `key`, поддерживается, старое значение политики для этого ключа приводятся к `unsigned int`.

### <a name="remarks"></a>Remarks

Метод вызовет исключение [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md) для недопустимого ключа политики или любого ключа политики, значение которого не может быть задано методом `SetPolicyValue`.

Метод вызывает [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) для значения, которое не поддерживается для ключа, указанного параметром `key`.

Обратите внимание, что этот метод не может устанавливать политики `MinConcurrency` или `MaxConcurrency`. Чтобы задать эти значения, используйте метод [сетконкурренцилимитс](#setconcurrencylimits) .

## <a name="see-also"></a>См. также раздел

[Пространство имен concurrency](concurrency-namespace.md)<br/>
[полициелементкэй](concurrency-namespace-enums.md)<br/>
[Класс CurrentScheduler](currentscheduler-class.md)<br/>
[Класс Scheduler](scheduler-class.md)<br/>
[Планировщик заданий](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)
