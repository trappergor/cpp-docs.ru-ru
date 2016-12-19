---
title: "Класс multitype_join | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::multitype_join"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "multitype_join - класс"
ms.assetid: 236e87a0-4867-49fd-869a-bef4010e49a7
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс multitype_join
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

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
 Тип объекта `join` это, либо блок `greedy` или `non_greedy`  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`type`|Псевдоним для `T`.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор multitype_join::multitype_join](#multitype_join__multitype_join_constructor)|Перегружен. Создает блок обмена сообщениями `multitype_join` .|  
|[multitype_join:: ~ multitype_join деструктор](#multitype_join___dtormultitype_join_destructor)|Уничтожает `multitype_join` блок обмена сообщениями.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод multitype_join::Accept](#multitype_join__accept_method)|Принимает сообщение, предложенное это `multitype_join` блоком, передавая владение вызывающему объекту.|  
|[Метод multitype_join::acquire_ref](#multitype_join__acquire_ref_method)|Получает значение счетчика ссылок на это `multitype_join` блок сообщений, чтобы предотвратить удаление.|  
|[Метод multitype_join::consume](#multitype_join__consume_method)|Потребляет сообщение, ранее предложенное `multitype_join` блок обмена сообщениями и успешно зарезервированное целевым объектом, передавая владение вызывающему объекту.|  
|[Метод multitype_join::link_target](#multitype_join__link_target_method)|Это связывает целевой блок `multitype_join` блок обмена сообщениями.|  
|[Метод multitype_join::Release](#multitype_join__release_method)|Освобождает предыдущее успешное резервирование сообщения.|  
|[Метод multitype_join::release_ref](#multitype_join__release_ref_method)|Освобождает значение счетчика ссылок на это `multiple_join` блок обмена сообщениями.|  
|[Метод multitype_join::reserve](#multitype_join__reserve_method)|Резервирует сообщение, которое было предложено это `multitype_join` блок обмена сообщениями.|  
|[Метод multitype_join::unlink_target](#multitype_join__unlink_target_method)|Удаляет связь целевого блока с это `multitype_join` блок обмена сообщениями.|  
|[Метод multitype_join::unlink_targets](#multitype_join__unlink_targets_method)|Удаляет связь всех целевых объектов из этого `multitype_join` блок обмена сообщениями. (Переопределяет [ISource::unlink_targets](../../../parallel/concrt/reference/isource-class.md#isource__unlink_targets_method).)|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 `multitype_join`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namemultitypejoinacceptmethoda-multitypejoinaccept-method"></a><a name="multitype_join__accept_method"></a>  Метод multitype_join::Accept  
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
  
##  <a name="a-namemultitypejoinacquirerefmethoda-multitypejoinacquireref-method"></a><a name="multitype_join__acquire_ref_method"></a>  Метод multitype_join::acquire_ref  
 Получает значение счетчика ссылок на это `multitype_join` блок сообщений, чтобы предотвратить удаление.  
  
```  
virtual void acquire_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на целевой блок, вызывающий этот метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается методом `ITarget` объекта, который связан с этим источником во время `link_target` метод.  
  
##  <a name="a-namemultitypejoinconsumemethoda-multitypejoinconsume-method"></a><a name="multitype_join__consume_method"></a>  Метод multitype_join::consume  
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
  `consume` Метод аналогичен методу `accept`, но всегда должно начинаться с помощью вызова `reserve` возвращается `true`.  
  
##  <a name="a-namemultitypejoinlinktargetmethoda-multitypejoinlinktarget-method"></a><a name="multitype_join__link_target_method"></a>  Метод multitype_join::link_target  
 Это связывает целевой блок `multitype_join` блок обмена сообщениями.  
  
```  
virtual void link_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на `ITarget` блок, чтобы создать ссылку на этот `multitype_join` блок обмена сообщениями.  
  
##  <a name="a-namemultitypejoinmultitypejoinconstructora-multitypejoinmultitypejoin-constructor"></a><a name="multitype_join__multitype_join_constructor"></a>  Конструктор multitype_join::multitype_join  
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
  
##  <a name="a-namemultitypejoindtormultitypejoindestructora-multitypejoinmultitypejoin-destructor"></a><a name="multitype_join___dtormultitype_join_destructor"></a>  multitype_join:: ~ multitype_join деструктор  
 Уничтожает `multitype_join` блок обмена сообщениями.  
  
```  
~multitype_join();
```  
  
##  <a name="a-namemultitypejoinreleasemethoda-multitypejoinrelease-method"></a><a name="multitype_join__release_method"></a>  Метод multitype_join::Release  
 Освобождает предыдущее успешное резервирование сообщения.  
  
```  
virtual void release(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
  `runtime_object_identity` Из `message` Объект освобожден.  
  
 `_PTarget`  
 Указатель на целевой блок, вызывающий `release` метод.  
  
##  <a name="a-namemultitypejoinreleaserefmethoda-multitypejoinreleaseref-method"></a><a name="multitype_join__release_ref_method"></a>  Метод multitype_join::release_ref  
 Освобождает значение счетчика ссылок на это `multiple_join` блок обмена сообщениями.  
  
```  
virtual void release_ref(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на целевой блок, вызывающий этот метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается методом `ITarget` объект, который является, связь которого с этим источником. Блок источника может освободить ресурсы, зарезервированные для целевой блок.  
  
##  <a name="a-namemultitypejoinreservemethoda-multitypejoinreserve-method"></a><a name="multitype_join__reserve_method"></a>  Метод multitype_join::reserve  
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
 `true` Если сообщение было успешно зарезервированы, `false` в противном случае. Резервирования могут завершаться неудачей по ряду причин, включая следующие: сообщение уже было зарезервировано или принято другим целевым объектом, источник может отклонять резервирования и т. п.  
  
### <a name="remarks"></a>Примечания  
 После вызова метода `reserve`, если он завершается успешно, необходимо вызвать либо `consume` или `release` Чтобы принять или высвободить владение сообщением, соответственно.  
  
##  <a name="a-namemultitypejoinunlinktargetmethoda-multitypejoinunlinktarget-method"></a><a name="multitype_join__unlink_target_method"></a>  Метод multitype_join::unlink_target  
 Удаляет связь целевого блока с это `multitype_join` блок обмена сообщениями.  
  
```  
virtual void unlink_target(_Inout_ ITarget<_Destination_type>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на `ITarget` блок отсоединиться от этого `multitype_join` блок обмена сообщениями.  
  
##  <a name="a-namemultitypejoinunlinktargetsmethoda-multitypejoinunlinktargets-method"></a><a name="multitype_join__unlink_targets_method"></a>  Метод multitype_join::unlink_targets  
 Удаляет связь всех целевых объектов из этого `multitype_join` блок обмена сообщениями.  
  
```  
virtual void unlink_targets();
```  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Класс Choice](../../../parallel/concrt/reference/choice-class.md)   
 [Класс JOIN](../Topic/join%20Class.md)
