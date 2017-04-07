---
title: "Класс SchedulerPolicy | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
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
caps.latest.revision: 22
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: a00f7d9cafbd84fc3bbf6b10f322fad6166110cd
ms.lasthandoff: 03/17/2017

---
# <a name="schedulerpolicy-class"></a>Класс SchedulerPolicy
Класс `SchedulerPolicy` содержит набор пар «ключ — значение» по одной для каждого элемента политики, управляющего поведением экземпляра планировщика.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class SchedulerPolicy;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[SchedulerPolicy](#ctor)|Перегружен. Создает новую политику планировщик и заполняет его значения для [ключи политики](concurrency-namespace-enums.md) поддерживаемых планировщиками среды параллелизма и диспетчером ресурсов.|  
|[~ Деструктор SchedulerPolicy](#dtor)|Удаляет политику планировщика.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[GetPolicyValue](#getpolicyvalue)|Извлекает значение ключа политики, предоставленные в качестве `key` параметр.|  
|[SetConcurrencyLimits](#setconcurrencylimits)|Одновременно задает `MinConcurrency` и `MaxConcurrency` политики на `SchedulerPolicy` объект.|  
|[SetPolicyValue](#setpolicyvalue)|Задает значение ключа политики, предоставленные в качестве `key` параметр и возвращает старое значение.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[operator=](#operator_eq)|Назначает политику планировщика из другой политики планировщика.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о политиках, которыми можно управлять с помощью `SchedulerPolicy` см. в разделе [PolicyElementKey](concurrency-namespace-enums.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `SchedulerPolicy`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h, concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="getpolicyvalue"></a>GetPolicyValue 

 Извлекает значение ключа политики, предоставленные в качестве `key` параметр.  
  
```
unsigned int GetPolicyValue(PolicyElementKey key) const;
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Ключ политики для извлечения значения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если ключ, указанный параметром `key` параметр поддерживается, значение политики для ключа приводит к `unsigned int`.  
  
### <a name="remarks"></a>Примечания  
 Метод создает исключение [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md) Недопустимая политика ключа.  
  
##  <a name="operator_eq"></a>оператор = 

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
  
##  <a name="ctor"></a>SchedulerPolicy 

 Создает новую политику планировщик и заполняет его значения для [ключи политики](concurrency-namespace-enums.md) поддерживаемых планировщиками среды параллелизма и диспетчером ресурсов.  
  
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
 Количество ключ значение пары, который следует за `_PolicyKeyCount` параметр.  
  
 `_SrcPolicy`  
 Политика источника для копирования.  
  
### <a name="remarks"></a>Примечания  
 Первый конструктор создает новую политику планировщика, где все политики будут инициализированы значениями по умолчанию.  
  
 Второй конструктор создает новую политику планировщика, которая использует стиль инициализации с именованными параметрами. Значения после `_PolicyKeyCount` параметр предоставляются в качестве пары «ключ значение». Любой ключ политики, который не указан в этом конструкторе будет иметь значение по умолчанию. Этот конструктор может вызывать исключения [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md), [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) или [invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md).  
  
 Третий конструктор является конструктор копий. Часто наиболее удобным способом для определения новой политики планировщика является копирование существующей политики и изменение ее методами `SetPolicyValue` или `SetConcurrencyLimits`.  
  
##  <a name="dtor"></a>~ SchedulerPolicy 

 Удаляет политику планировщика.  
  
```
~SchedulerPolicy();
```  
  
##  <a name="setconcurrencylimits"></a>SetConcurrencyLimits 

 Одновременно задает `MinConcurrency` и `MaxConcurrency` политики на `SchedulerPolicy` объект.  
  
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
 Метод создает исключение [invalid_scheduler_policy_thread_specification](invalid-scheduler-policy-thread-specification-class.md) Если значение, указанное для `MinConcurrency` политика больше, чем указано для `MaxConcurrency` политики.  
  
 Можно также вызвать метод [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) для других недопустимых значений.  
  
##  <a name="setpolicyvalue"></a>SetPolicyValue 

 Задает значение ключа политики, предоставленные в качестве `key` параметр и возвращает старое значение.  
  
```
unsigned int SetPolicyValue(
    PolicyElementKey key,
    unsigned int value);
```  
  
### <a name="parameters"></a>Параметры  
 `key`  
 Ключ политики, чтобы задать значение для.  
  
 `value`  
 Значение, задайте ключ политики.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Если ключ, указанный параметром `key` параметр поддерживается, старый значение политики для ключа приводит к `unsigned int`.  
  
### <a name="remarks"></a>Примечания  
 Метод создает исключение [invalid_scheduler_policy_key](invalid-scheduler-policy-key-class.md) ключ Недопустимая политика или любой ключ политики, значение которого не может устанавливаться `SetPolicyValue` метод.  
  
 Метод создает исключение [invalid_scheduler_policy_value](invalid-scheduler-policy-value-class.md) значения, которое не поддерживается для ключа, заданного параметром `key` параметр.  
  
 Обратите внимание, что этот метод не может быть значение `MinConcurrency` или `MaxConcurrency` политики. Чтобы задать эти значения, используйте [SetConcurrencyLimits](#setconcurrencylimits) метод.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [PolicyElementKey](concurrency-namespace-enums.md)   
 [Класс CurrentScheduler](currentscheduler-class.md)   
 [Класс планировщика](scheduler-class.md)   
 [Планировщик заданий](../../../parallel/concrt/task-scheduler-concurrency-runtime.md)




