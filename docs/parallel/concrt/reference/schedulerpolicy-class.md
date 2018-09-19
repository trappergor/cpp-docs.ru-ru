---
title: Класс SchedulerPolicy | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: d7cf95898afa5e669d52b8bf18ad0cfc8733cb37
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46076272"
---
# <a name="schedulerpolicy-class"></a>Класс SchedulerPolicy
Класс `SchedulerPolicy` содержит набор пар «ключ — значение» по одной для каждого элемента политики, управляющего поведением экземпляра планировщика.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class SchedulerPolicy;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[SchedulerPolicy](#ctor)|Перегружен. Создает новую политику планировщик и заполняет его значения для [ключи политики](concurrency-namespace-enums.md) поддерживаемых планировщиков исполняющей среды с параллелизмом и Resource Manager.|  
|[~ Деструктор SchedulerPolicy](#dtor)|Уничтожает политики планировщика.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[GetPolicyValue](#getpolicyvalue)|Извлекает значение ключа политики передано в качестве `key` параметра.|  
|[SetConcurrencyLimits](#setconcurrencylimits)|Одновременно задает `MinConcurrency` и `MaxConcurrency` политики на `SchedulerPolicy` объекта.|  
|[SetPolicyValue](#setpolicyvalue)|Задает значение ключа политики передано в качестве `key` параметр и возвращает старое значение.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[оператор=](#operator_eq)|Назначает политики планировщика из другой политики планировщика.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о политиках, которыми можно управлять с помощью `SchedulerPolicy` , представлена в разделе [PolicyElementKey](concurrency-namespace-enums.md).  
  
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
*key*<br/>
Ключ политики для получения значений.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если ключ, указанный параметром `key` параметр поддерживается, значение политики для ключа приводит к `unsigned int`.  
  
### <a name="remarks"></a>Примечания  
 Метод вызовет [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md) для ключа Недопустимая политика.  
  
##  <a name="operator_eq"></a> оператор = 

 Назначает политики планировщика из другой политики планировщика.  
  
```
SchedulerPolicy& operator= (const SchedulerPolicy& _RhsPolicy);
```  
  
### <a name="parameters"></a>Параметры  
*_RhsPolicy*<br/>
Политики, чтобы назначить эту политику.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на политику планировщика.  
  
### <a name="remarks"></a>Примечания  
 Часто наиболее удобным способом для определения новой политики планировщика является копирование существующей политики и изменение ее методами `SetPolicyValue` или `SetConcurrencyLimits`.  
  
##  <a name="ctor"></a> SchedulerPolicy 

 Создает новую политику планировщик и заполняет его значения для [ключи политики](concurrency-namespace-enums.md) поддерживаемых планировщиков исполняющей среды с параллелизмом и Resource Manager.  
  
```
SchedulerPolicy();

SchedulerPolicy(
    size_t _PolicyKeyCount,
 ...);

SchedulerPolicy(
    const SchedulerPolicy& _SrcPolicy);
```  
  
### <a name="parameters"></a>Параметры  
*_PolicyKeyCount*<br/>
Число ключей и значений в виде пары ниже `_PolicyKeyCount` параметра.  
  
*_SrcPolicy*<br/>
Исходная политика для копирования.  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор создает новую политику планировщика, где все политики будут инициализированы значениями по умолчанию.  
  
 Второй конструктор создает новую политику планировщика, использующий стиль с именем параметра инициализации. Значения после `_PolicyKeyCount` параметра передаются в виде пар "ключ значение". Любой ключ политики, который не указан в этом конструкторе будет иметь значение по умолчанию. Этот конструктор может вызывать исключения [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md), [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) или [invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md).  
  
 Третий конструктор является конструктором копии. Часто наиболее удобным способом для определения новой политики планировщика является копирование существующей политики и изменение ее методами `SetPolicyValue` или `SetConcurrencyLimits`.  
  
##  <a name="dtor"></a> ~ SchedulerPolicy 

 Уничтожает политики планировщика.  
  
```
~SchedulerPolicy();
```  
  
##  <a name="setconcurrencylimits"></a> SetConcurrencyLimits 

 Одновременно задает `MinConcurrency` и `MaxConcurrency` политики на `SchedulerPolicy` объекта.  
  
```
void SetConcurrencyLimits(
    unsigned int _MinConcurrency,
    unsigned int _MaxConcurrency = MaxExecutionResources);
```  
  
### <a name="parameters"></a>Параметры  
*_MinConcurrency*<br/>
Значение для `MinConcurrency` ключ политики.  
  
*_MaxConcurrency*<br/>
Значение для `MaxConcurrency` ключ политики.  
  
### <a name="remarks"></a>Примечания  
 Метод вызовет [invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md) Если значение, заданное для `MinConcurrency` политики больше, чем указано для `MaxConcurrency` политики.  
  
 Метод также может породить [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) для других недопустимых значений.  
  
##  <a name="setpolicyvalue"></a> SetPolicyValue 

 Задает значение ключа политики передано в качестве `key` параметр и возвращает старое значение.  
  
```
unsigned int SetPolicyValue(
    PolicyElementKey key,
    unsigned int value);
```  
  
### <a name="parameters"></a>Параметры  
*key*<br/>
Ключ политики, чтобы задать значение для.  
  
*значение*<br/>
Задаваемое значение ключа политики.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если ключ, указанный параметром `key` параметр поддерживается, старое значение политики для ключа приводит к `unsigned int`.  
  
### <a name="remarks"></a>Примечания  
 Метод вызовет [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md) ключ Недопустимая политика или любой ключ политики, значение которого не может задать `SetPolicyValue` метод.  
  
 Метод вызовет [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) значения, которое не поддерживается для ключа, заданного параметром `key` параметр.  
  
 Обратите внимание, что этот метод не разрешен для задания `MinConcurrency` или `MaxConcurrency` политики. Чтобы задать эти значения, используйте [SetConcurrencyLimits](#setconcurrencylimits) метод.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [Класс CurrentScheduler](currentscheduler-class.md)   
 [Класс Scheduler](scheduler-class.md)   
 [Планировщик задач](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)



