---
title: "Класс SchedulerPolicy | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- SchedulerPolicy
- concrt/concurrency::SchedulerPolicy
- concrt/concurrency::SchedulerPolicy::SchedulerPolicy
- concrt/concurrency::SchedulerPolicy::GetPolicyValue
- concrt/concurrency::SchedulerPolicy::SetConcurrencyLimits
- concrt/concurrency::SchedulerPolicy::SetPolicyValue
dev_langs:
- C++
helpviewer_keywords:
- SchedulerPolicy class
ms.assetid: bcebf51a-65f8-45a3-809b-d1ff93527dc4
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 6fc8873fc4516b3c79685eacc91d3d4426b80901
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="schedulerpolicy-class"></a>Класс SchedulerPolicy
Класс `SchedulerPolicy` содержит набор пар «ключ — значение» по одной для каждого элемента политики, управляющего поведением экземпляра планировщика.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class SchedulerPolicy;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[SchedulerPolicy](#ctor)|Перегружен. Создает новую политику планировщик и заполняет ее значения для [ключей политики](concurrency-namespace-enums.md) поддерживаемые планировщики среда выполнения с параллелизмом и диспетчер ресурсов.|  
|[~ Деструктор SchedulerPolicy](#dtor)|Удаляет политики планировщика.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[GetPolicyValue](#getpolicyvalue)|Извлекает значение ключа политики передано в качестве `key` параметра.|  
|[SetConcurrencyLimits](#setconcurrencylimits)|Одновременно задает `MinConcurrency` и `MaxConcurrency` политик на `SchedulerPolicy` объекта.|  
|[SetPolicyValue](#setpolicyvalue)|Задает значение параметра политики задано как `key` параметр и возвращает старое значение.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[оператор=](#operator_eq)|Назначает политику планировщика из другой политики планировщика.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о политиках, которые могут управляться с помощью `SchedulerPolicy` см. в описании [PolicyElementKey](concurrency-namespace-enums.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `SchedulerPolicy`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h, concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="getpolicyvalue"></a> GetPolicyValue 

 Извлекает значение ключа политики передано в качестве `key` параметра.  
  
```
unsigned int GetPolicyValue(PolicyElementKey key) const;
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Ключ политики для извлечения значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если ключ, указанный параметром `key` параметр поддерживается, значение политики для ключа приводит к `unsigned int`.  
  
### <a name="remarks"></a>Примечания  
 Метод вызывает исключение [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md) для ключа Недопустимая политика.  
  
##  <a name="operator_eq"></a> оператор = 

 Назначает политику планировщика из другой политики планировщика.  
  
```
SchedulerPolicy& operator= (const SchedulerPolicy& _RhsPolicy);
```  
  
### <a name="parameters"></a>Параметры  
 `_RhsPolicy`  
 Политика для назначения этой политике.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на политику планировщика.  
  
### <a name="remarks"></a>Примечания  
 Часто наиболее удобным способом для определения новой политики планировщика является копирование существующей политики и изменение ее методами `SetPolicyValue` или `SetConcurrencyLimits`.  
  
##  <a name="ctor"></a> SchedulerPolicy 

 Создает новую политику планировщик и заполняет ее значения для [ключей политики](concurrency-namespace-enums.md) поддерживаемые планировщики среда выполнения с параллелизмом и диспетчер ресурсов.  
  
```
SchedulerPolicy();

SchedulerPolicy(
    size_t _PolicyKeyCount,
 ...);

SchedulerPolicy(
    const SchedulerPolicy& _SrcPolicy);
```  
  
### <a name="parameters"></a>Параметры  
 `_PolicyKeyCount`  
 Число ключей и значений пар ниже `_PolicyKeyCount` параметра.  
  
 `_SrcPolicy`  
 Политика источника для копирования.  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор создает новую политику планировщика, где все политики, будут присвоены значения по умолчанию.  
  
 Второй конструктор создает новую политику планировщика, которая использует стиль с именем параметра инициализации. Значения после `_PolicyKeyCount` параметров передаются в виде пар "ключ значение". Любой ключ политики, который не указан в этом конструкторе будет иметь значение по умолчанию. Этот конструктор может вызывать исключения [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md), [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) или [invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md).  
  
 Третий конструктор является конструктором копирования. Часто наиболее удобным способом для определения новой политики планировщика является копирование существующей политики и изменение ее методами `SetPolicyValue` или `SetConcurrencyLimits`.  
  
##  <a name="dtor"></a> ~SchedulerPolicy 

 Удаляет политики планировщика.  
  
```
~SchedulerPolicy();
```  
  
##  <a name="setconcurrencylimits"></a> SetConcurrencyLimits 

 Одновременно задает `MinConcurrency` и `MaxConcurrency` политик на `SchedulerPolicy` объекта.  
  
```
void SetConcurrencyLimits(
    unsigned int _MinConcurrency,
    unsigned int _MaxConcurrency = MaxExecutionResources);
```  
  
### <a name="parameters"></a>Параметры  
 `_MinConcurrency`  
 Значение для `MinConcurrency` ключ политики.  
  
 `_MaxConcurrency`  
 Значение для `MaxConcurrency` ключ политики.  
  
### <a name="remarks"></a>Примечания  
 Метод вызывает исключение [invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md) Если значение, указанное для `MinConcurrency` политики больше, чем указано для `MaxConcurrency` политики.  
  
 Метод также может вызвать исключение [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) другие недопустимые значения.  
  
##  <a name="setpolicyvalue"></a> SetPolicyValue 

 Задает значение параметра политики задано как `key` параметр и возвращает старое значение.  
  
```
unsigned int SetPolicyValue(
    PolicyElementKey key,
    unsigned int value);
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Ключ для установки значения для политики.  
  
 `value`  
 Значение присваивается ключу политики.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если ключ, указанный параметром `key` параметр поддерживается, старое значение политики для ключа приводит к `unsigned int`.  
  
### <a name="remarks"></a>Примечания  
 Метод вызывает исключение [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md) ключ Недопустимая политика или любой политики ключ, значение которого не может задаваться `SetPolicyValue` метод.  
  
 Метод вызывает исключение [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) значения, которое не поддерживается для ключа, заданного параметром `key` параметр.  
  
 Обратите внимание, что этот метод не разрешен для задания `MinConcurrency` или `MaxConcurrency` политики. Чтобы задать эти значения, используйте [SetConcurrencyLimits](#setconcurrencylimits) метод.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [Класс CurrentScheduler](currentscheduler-class.md)   
 [Класс Scheduler](scheduler-class.md)   
 [Планировщик задач](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)



