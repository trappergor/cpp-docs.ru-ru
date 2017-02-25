---
title: "Класс choice | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "agents/concurrency::choice"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "choice - класс"
ms.assetid: 4157a539-d5c2-4161-b1ab-536ce2888397
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 21
---
# Класс choice
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Блок обмена сообщениями `choice` — это блок с несколькими источниками и одной целью, который представляет взаимодействие потока управления с набором источников. Блок choice будет ожидать доступа к любому из нескольких источников для создания сообщения и распространит индекс источника, создавшего сообщение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<
    class T  
>  
class choice: public ISource<size_t>;  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 A `tuple`-на основе типа, представляющий полезные нагрузки входных источников.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`type`|Псевдоним для `T`.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор Choice::choice](#choice__choice_constructor)|Перегружен. Создает блок обмена сообщениями `choice` .|  
|[Выбор:: ~ choice деструктор](#choice___dtorchoice_destructor)|Уничтожает `choice` блок обмена сообщениями.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод Choice::Accept](#choice__accept_method)|Принимает сообщение, предложенное это `choice` блоком, передавая владение вызывающему объекту.|  
|[Метод Choice::acquire_ref](#choice__acquire_ref_method)|Получает значение счетчика ссылок на это `choice` блок сообщений, чтобы предотвратить удаление.|  
|[Метод Choice::consume](#choice__consume_method)|Потребляет сообщение, ранее предложенное это `choice` блок обмена сообщениями и успешно зарезервированное целевым объектом, передавая владение вызывающему объекту.|  
|[Метод Choice::has_value](#choice__has_value_method)|Проверяет, является ли это `choice` блок сообщений еще инициализирован со значением.|  
|[Метод Choice::index](#choice__index_method)|Возвращает индекс в `tuple` представляет элемент, выбранный по `choice` блок обмена сообщениями.|  
|[Метод Choice::link_target](#choice__link_target_method)|Это связывает целевой блок `choice` блок обмена сообщениями.|  
|[Метод Choice::Release](#choice__release_method)|Освобождает предыдущее успешное резервирование сообщения.|  
|[Метод Choice::release_ref](#choice__release_ref_method)|Освобождает значение счетчика ссылок на это `choice` блок обмена сообщениями.|  
|[Метод Choice::reserve](#choice__reserve_method)|Резервирует сообщение, которое было предложено это `choice` блок обмена сообщениями.|  
|[Метод Choice::unlink_target](#choice__unlink_target_method)|Удаляет связь целевого блока с это `choice` блок обмена сообщениями.|  
|[Метод Choice::unlink_targets](#choice__unlink_targets_method)|Удаляет связь всех целевых объектов из этого `choice` блок обмена сообщениями. (Переопределяет [ISource::unlink_targets](../../../parallel/concrt/reference/isource-class.md#isource__unlink_targets_method).)|  
|[Метод Choice::value](#choice__value_method)|Получает сообщение, индекс которого был выбран, `choice` блок обмена сообщениями.|  
  
## <a name="remarks"></a>Примечания  
 Блок выбора гарантирует, что используется только одно из входящих сообщений.  
  
 Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [ISource](../../../parallel/concrt/reference/isource-class.md)  
  
 `choice`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namechoiceacceptmethoda-choiceaccept-method"></a><a name="choice__accept_method"></a>  Метод Choice::Accept  
 Принимает сообщение, предложенное это `choice` блоком, передавая владение вызывающему объекту.  
  
```  
virtual message<size_t>* accept(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
  `runtime_object_identity` Из предложенных `message` объекта.  
  
 `_PTarget`  
 Указатель на целевой блок, вызывающий `accept` метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на сообщение, которое теперь принадлежит вызывающей стороне.  
  
##  <a name="a-namechoiceacquirerefmethoda-choiceacquireref-method"></a><a name="choice__acquire_ref_method"></a>  Метод Choice::acquire_ref  
 Получает значение счетчика ссылок на это `choice` блок сообщений, чтобы предотвратить удаление.  
  
```  
virtual void acquire_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на целевой блок, вызывающий этот метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается методом `ITarget` объекта, который связан с этим источником во время `link_target` метод.  
  
##  <a name="a-namechoicechoiceconstructora-choicechoice-constructor"></a><a name="choice__choice_constructor"></a>  Конструктор Choice::choice  
 Создает блок обмена сообщениями `choice` .  
  
```  
explicit choice(
    T _Tuple);

 
choice(
    Scheduler& _PScheduler,  
    T _Tuple);

 
choice(
    ScheduleGroup& _PScheduleGroup,  
    T _Tuple);

 
choice(
    choice&& _Choice);
```  
  
### <a name="parameters"></a>Параметры  
 `_Tuple`  
 Объект `tuple` источников по выбору.  
  
 `_PScheduler`  
 Объект `Scheduler` , в котором запланирована задача распространения для блока обмена сообщениями `choice` .  
  
 `_PScheduleGroup`  
 Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `choice` . Используемый объект `Scheduler` подразумевается группой расписаний.  
  
 `_Choice`  
 Блок обмена сообщениями `choice` , из которого выполняется копирование. Обратите внимание, что исходный объект становится потерянным, превращая этот конструктор в конструктор перемещения.  
  
### <a name="remarks"></a>Примечания  
 Среда выполнения использует планировщик по умолчанию, если вы не указали параметры `_PScheduler` или `_PScheduleGroup` .  
  
 Конструкция перемещения не выполняется при блокировке. Это означает, что пользователь должен убедиться в отсутствии простых задач во время перемещения. В противном случае могут возникнуть многочисленные гонки, приводящие к исключениям или недопустимому состоянию.  
  
##  <a name="a-namechoicedtorchoicedestructora-choicechoice-destructor"></a><a name="choice___dtorchoice_destructor"></a>  Выбор:: ~ choice деструктор  
 Уничтожает `choice` блок обмена сообщениями.  
  
```  
~choice();
```  
  
##  <a name="a-namechoiceconsumemethoda-choiceconsume-method"></a><a name="choice__consume_method"></a>  Метод Choice::consume  
 Потребляет сообщение, ранее предложенное это `choice` блок обмена сообщениями и успешно зарезервированное целевым объектом, передавая владение вызывающему объекту.  
  
```  
virtual message<size_t>* consume(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
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
  
##  <a name="a-namechoicehasvaluemethoda-choicehasvalue-method"></a><a name="choice__has_value_method"></a>  Метод Choice::has_value  
 Проверяет, является ли это `choice` блок сообщений еще инициализирован со значением.  
  
```  
bool has_value() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если блок получил значение, `false` в противном случае.  
  
##  <a name="a-namechoiceindexmethoda-choiceindex-method"></a><a name="choice__index_method"></a>  Метод Choice::index  
 Возвращает индекс в `tuple` представляет элемент, выбранный по `choice` блок обмена сообщениями.  
  
```  
size_t index();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс сообщения.  
  
### <a name="remarks"></a>Примечания  
 Полезные данные сообщения могут быть извлечены с помощью `get` метод.  
  
##  <a name="a-namechoicelinktargetmethoda-choicelinktarget-method"></a><a name="choice__link_target_method"></a>  Метод Choice::link_target  
 Это связывает целевой блок `choice` блок обмена сообщениями.  
  
```  
virtual void link_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на `ITarget` блок, чтобы создать ссылку на этот `choice` блок обмена сообщениями.  
  
##  <a name="a-namechoicereleasemethoda-choicerelease-method"></a><a name="choice__release_method"></a>  Метод Choice::Release  
 Освобождает предыдущее успешное резервирование сообщения.  
  
```  
virtual void release(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
  `runtime_object_identity` Из `message` Объект освобожден.  
  
 `_PTarget`  
 Указатель на целевой блок, вызывающий `release` метод.  
  
##  <a name="a-namechoicereleaserefmethoda-choicereleaseref-method"></a><a name="choice__release_ref_method"></a>  Метод Choice::release_ref  
 Освобождает значение счетчика ссылок на это `choice` блок обмена сообщениями.  
  
```  
virtual void release_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на целевой блок, вызывающий этот метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается методом `ITarget` объект, который является, связь которого с этим источником. Блок источника может освободить ресурсы, зарезервированные для целевой блок.  
  
##  <a name="a-namechoicereservemethoda-choicereserve-method"></a><a name="choice__reserve_method"></a>  Метод Choice::reserve  
 Резервирует сообщение, которое было предложено это `choice` блок обмена сообщениями.  
  
```  
virtual bool reserve(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
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
  
##  <a name="a-namechoiceunlinktargetmethoda-choiceunlinktarget-method"></a><a name="choice__unlink_target_method"></a>  Метод Choice::unlink_target  
 Удаляет связь целевого блока с это `choice` блок обмена сообщениями.  
  
```  
virtual void unlink_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на `ITarget` блок отсоединиться от этого `choice` блок обмена сообщениями.  
  
##  <a name="a-namechoiceunlinktargetsmethoda-choiceunlinktargets-method"></a><a name="choice__unlink_targets_method"></a>  Метод Choice::unlink_targets  
 Удаляет связь всех целевых объектов из этого `choice` блок обмена сообщениями.  
  
```  
virtual void unlink_targets();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод не вызывается из деструктора, поскольку деструктор для внутреннего `single_assignment` блок будет разрывать связь правильно.  
  
##  <a name="a-namechoicevaluemethoda-choicevalue-method"></a><a name="choice__value_method"></a>  Метод Choice::value  
 Получает сообщение, индекс которого был выбран, `choice` блок обмена сообщениями.  
  
```  
template <
    typename _Payload_type  
>  
_Payload_type const& value();
```  
  
### <a name="parameters"></a>Параметры  
 `_Payload_type`  
 Тип полезных данных сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Полезные данные сообщения.  
  
### <a name="remarks"></a>Примечания  
 Поскольку блок сообщений `choice` может принимать входные данные с различными типами полезной нагрузки, необходимо указать тип полезной нагрузки в момент извлечения. Можно определить тип, основанный на результате `index` метод.  
  
## <a name="see-also"></a>См. также раздел  
 [пространство имен Concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Класс JOIN](../Topic/join%20Class.md)   
 [Класс single_assignment](../../../parallel/concrt/reference/single-assignment-class.md)
