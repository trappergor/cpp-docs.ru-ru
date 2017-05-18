---
title: "Класс multitype_join | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- multitype_join
- AGENTS/concurrency::multitype_join
- AGENTS/concurrency::multitype_join::multitype_join
- AGENTS/concurrency::multitype_join::accept
- AGENTS/concurrency::multitype_join::acquire_ref
- AGENTS/concurrency::multitype_join::consume
- AGENTS/concurrency::multitype_join::link_target
- AGENTS/concurrency::multitype_join::release
- AGENTS/concurrency::multitype_join::release_ref
- AGENTS/concurrency::multitype_join::reserve
- AGENTS/concurrency::multitype_join::unlink_target
- AGENTS/concurrency::multitype_join::unlink_targets
dev_langs:
- C++
helpviewer_keywords:
- multitype_join class
ms.assetid: 236e87a0-4867-49fd-869a-bef4010e49a7
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 03cb8520f9c4511aaff238f672f77b74b623b349
ms.contentlocale: ru-ru
ms.lasthandoff: 03/17/2017

---
# <a name="multitypejoin-class"></a>Класс multitype_join
Блок обмена сообщениями `multitype_join` — это блок с несколькими источниками и одной целью, который объединяет сообщения разных типов от каждого из своих источников и предлагает кортеж объединенных сообщений своему целевому объекту.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<
    typename T,  
    join_type _Jtype = non_greedy  
>  
class multitype_join: public ISource<typename _Unwrap<T>::type>;  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 `tuple` Тип полезных данных сообщений, объединенных и распространенных блоком.  
  
 `_Jtype`  
 Тип объекта `join` это, либо блок `greedy` или`non_greedy`  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`type`|Псевдоним для `T`.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[multitype_join](#ctor)|Перегружен. Создает блок обмена сообщениями `multitype_join` .|  
|[~ multitype_join деструктор](#dtor)|Уничтожает `multitype_join` блок обмена сообщениями.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[принять](#accept)|Принимает сообщение, предложенное это `multitype_join` блоком, передавая владение вызывающему объекту.|  
|[acquire_ref](#acquire_ref)|Получает значение счетчика ссылок на это `multitype_join` блок сообщений, чтобы предотвратить удаление.|  
|[Использование](#consume)|Потребляет сообщение, ранее предложенное `multitype_join` блок обмена сообщениями и успешно зарезервированное целевым объектом, передавая владение вызывающему объекту.|  
|[link_target](#link_target)|Это связывает целевой блок `multitype_join` блок обмена сообщениями.|  
|[release](#release)|Освобождает предыдущее успешное резервирование сообщения.|  
|[release_ref](#release_ref)|Освобождает значение счетчика ссылок на это `multiple_join` блок обмена сообщениями.|  
|[reserve](#reserve)|Резервирует сообщение, которое было предложено это `multitype_join` блок обмена сообщениями.|  
|[unlink_target](#unlink_target)|Удаляет связь целевого блока с это `multitype_join` блок обмена сообщениями.|  
|[unlink_targets](#unlink_targets)|Удаляет связь всех целевых объектов из этого `multitype_join` блок обмена сообщениями. (Переопределяет [ISource::unlink_targets](isource-class.md#unlink_targets).)|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [ISource](isource-class.md)  
  
 `multitype_join`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="accept"></a>принять 

 Принимает сообщение, предложенное это `multitype_join` блоком, передавая владение вызывающему объекту.  
  
```  
virtual message<_Destination_type>* accept(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из предложенных `message` объекта.  
  
 `_PTarget`  
 Указатель на целевой блок, вызывающий `accept` метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на сообщение, которое теперь принадлежит вызывающей стороне.  
  
##  <a name="acquire_ref"></a>acquire_ref 

 Получает значение счетчика ссылок на это `multitype_join` блок сообщений, чтобы предотвратить удаление.  
  
```  
virtual void acquire_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на целевой блок, вызывающий этот метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается методом `ITarget` объекта, который связан с этим источником во время `link_target` метод.  
  
##  <a name="consume"></a>Использование 

 Потребляет сообщение, ранее предложенное `multitype_join` блок обмена сообщениями и успешно зарезервированное целевым объектом, передавая владение вызывающему объекту.  
  
```  
virtual message<_Destination_type>* consume(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Зарезервированных `message` объекта.  
  
 `_PTarget`  
 Указатель на целевой блок, вызывающий `consume` метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `message` объект, вызывающий теперь принадлежит.  
  
### <a name="remarks"></a>Примечания  
 `consume` Метод аналогичен `accept`, но всегда должно начинаться с помощью вызова `reserve` , возвращается `true`.  
  
##  <a name="link_target"></a>link_target 

 Это связывает целевой блок `multitype_join` блок обмена сообщениями.  
  
```  
virtual void link_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на `ITarget` блок, чтобы создать ссылку на этот `multitype_join` блок обмена сообщениями.  
  
##  <a name="ctor"></a>multitype_join 

 Создает блок обмена сообщениями `multitype_join` .  
  
```  
explicit multitype_join(
    T _Tuple);

 
multitype_join(
    Scheduler& _PScheduler,  
    T _Tuple);

 
multitype_join(
    ScheduleGroup& _PScheduleGroup,  
    T _Tuple);

 
multitype_join(
    multitype_join&& _Join);
```  
  
### <a name="parameters"></a>Параметры  
 `_Tuple`  
 Объект `tuple` источников для этого блока обмена сообщениями `multitype_join` .  
  
 `_PScheduler`  
 Объект `Scheduler` , в котором запланирована задача распространения для блока обмена сообщениями `multitype_join` .  
  
 `_PScheduleGroup`  
 Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `multitype_join` . Используемый объект `Scheduler` подразумевается группой расписаний.  
  
 `_Join`  
 Блок обмена сообщениями `multitype_join` , из которого выполняется копирование. Обратите внимание, что исходный объект становится потерянным, превращая этот конструктор в конструктор перемещения.  
  
### <a name="remarks"></a>Примечания  
 Среда выполнения использует планировщик по умолчанию, если вы не указали параметры `_PScheduler` или `_PScheduleGroup` .  
  
 Конструкция перемещения не выполняется при блокировке. Это означает, что пользователь должен убедиться в отсутствии простых задач во время перемещения. В противном случае могут возникнуть многочисленные гонки, приводящие к исключениям или недопустимому состоянию.  
  
##  <a name="dtor"></a>~ multitype_join 

 Уничтожает `multitype_join` блок обмена сообщениями.  
  
```  
~multitype_join();
```  
  
##  <a name="release"></a>выпуск 

 Освобождает предыдущее успешное резервирование сообщения.  
  
```  
virtual void release(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из `message` объект освобожден.  
  
 `_PTarget`  
 Указатель на целевой блок, вызывающий `release` метод.  
  
##  <a name="release_ref"></a>release_ref 

 Освобождает значение счетчика ссылок на это `multiple_join` блок обмена сообщениями.  
  
```  
virtual void release_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на целевой блок, вызывающий этот метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается методом `ITarget` объект, который является, связь которого с этим источником. Блок источника может освободить ресурсы, зарезервированные для целевой блок.  
  
##  <a name="reserve"></a>Резерв 

 Резервирует сообщение, которое было предложено это `multitype_join` блок обмена сообщениями.  
  
```  
virtual bool reserve(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из `message` объекта резервируются.  
  
 `_PTarget`  
 Указатель на целевой блок, вызывающий `reserve` метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если сообщение было успешно зарезервированы, `false` в противном случае. Резервирования могут завершаться неудачей по ряду причин, включая следующие: сообщение уже было зарезервировано или принято другим целевым объектом, источник может отклонять резервирования и т. п.  
  
### <a name="remarks"></a>Примечания  
 После вызова метода `reserve`, если он завершается успешно, необходимо вызвать либо `consume` или `release` чтобы принять или высвободить владение сообщением, соответственно.  
  
##  <a name="unlink_target"></a>unlink_target 

 Удаляет связь целевого блока с это `multitype_join` блок обмена сообщениями.  
  
```  
virtual void unlink_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на `ITarget` блок отсоединиться от этого `multitype_join` блок обмена сообщениями.  
  
##  <a name="unlink_targets"></a>unlink_targets 

 Удаляет связь всех целевых объектов из этого `multitype_join` блок обмена сообщениями.  
  
```  
virtual void unlink_targets();
```  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс Choice](choice-class.md)   
 [Класс join](join-class.md)

