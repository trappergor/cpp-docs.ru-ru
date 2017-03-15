---
title: "Класс Choice | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::choice
dev_langs:
- C++
helpviewer_keywords:
- choice class
ms.assetid: 4157a539-d5c2-4161-b1ab-536ce2888397
caps.latest.revision: 21
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 1ee8fe2197a41ad2abc14e24c372f808bdbc16d0
ms.lasthandoff: 02/24/2017

---
# <a name="choice-class"></a>Класс choice
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
|[Выбор конструктора](#ctor)|Перегружен. Создает блок обмена сообщениями `choice` .|  
|[~ choice деструктор](#dtor)|Уничтожает `choice` блок обмена сообщениями.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Accept-метод](#accept)|Принимает сообщение, предложенное это `choice` блоком, передавая владение вызывающему объекту.|  
|[acquire_ref метод](#acquire_ref)|Получает значение счетчика ссылок на это `choice` блок сообщений, чтобы предотвратить удаление.|  
|[consume-метод](#consume)|Потребляет сообщение, ранее предложенное это `choice` блок обмена сообщениями и успешно зарезервированное целевым объектом, передавая владение вызывающему объекту.|  
|[has_value метод](#has_value)|Проверяет, является ли это `choice` блок сообщений еще инициализирован со значением.|  
|[Метод Index](#index)|Возвращает индекс в `tuple` представляет элемент, выбранный по `choice` блок обмена сообщениями.|  
|[Метод link_target](#link_target)|Это связывает целевой блок `choice` блок обмена сообщениями.|  
|[Release-метод](#release)|Освобождает предыдущее успешное резервирование сообщения.|  
|[release_ref метод](#release_ref)|Освобождает значение счетчика ссылок на это `choice` блок обмена сообщениями.|  
|[reserve-метод](#reserve)|Резервирует сообщение, которое было предложено это `choice` блок обмена сообщениями.|  
|[unlink_target метод](#unlink_target)|Удаляет связь целевого блока с это `choice` блок обмена сообщениями.|  
|[unlink_targets метод](#unlink_targets)|Удаляет связь всех целевых объектов из этого `choice` блок обмена сообщениями. (Переопределяет [ISource::unlink_targets](isource-class.md#unlink_targets).)|  
|[значение метода](#value)|Получает сообщение, индекс которого был выбран, `choice` блок обмена сообщениями.|  
  
## <a name="remarks"></a>Примечания  
 Блок выбора гарантирует, что используется только одно из входящих сообщений.  
  
 Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [ISource](isource-class.md)  
  
 `choice`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-nameaccepta-accept"></a><a name="accept"></a>принять 

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
  
##  <a name="a-nameacquirerefa-acquireref"></a><a name="acquire_ref"></a>acquire_ref 

 Получает значение счетчика ссылок на это `choice` блок сообщений, чтобы предотвратить удаление.  
  
```  
virtual void acquire_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на целевой блок, вызывающий этот метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается методом `ITarget` объекта, который связан с этим источником во время `link_target` метод.  
  
##  <a name="a-namectora-choice"></a><a name="ctor"></a>Выбор 

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
  
##  <a name="a-namedtora-choice"></a><a name="dtor"></a>~ choice 

 Уничтожает `choice` блок обмена сообщениями.  
  
```  
~choice();
```  
  
##  <a name="a-nameconsumea-consume"></a><a name="consume"></a>Использование 

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
 `consume` Метод аналогичен `accept`, но всегда должно начинаться с помощью вызова `reserve` , возвращается `true`.  
  
##  <a name="a-namehasvaluea-hasvalue"></a><a name="has_value"></a>has_value 

 Проверяет, является ли это `choice` блок сообщений еще инициализирован со значением.  
  
```  
bool has_value() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если блок получил значение, `false` в противном случае.  
  
##  <a name="a-nameindexa-index"></a><a name="index"></a>Индекс 

 Возвращает индекс в `tuple` представляет элемент, выбранный по `choice` блок обмена сообщениями.  
  
```  
size_t index();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс сообщения.  
  
### <a name="remarks"></a>Примечания  
 Полезные данные сообщения могут быть извлечены с помощью `get` метод.  
  
##  <a name="a-namelinktargeta-linktarget"></a><a name="link_target"></a>link_target 

 Это связывает целевой блок `choice` блок обмена сообщениями.  
  
```  
virtual void link_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на `ITarget` блок, чтобы создать ссылку на этот `choice` блок обмена сообщениями.  
  
##  <a name="a-namereleasea-release"></a><a name="release"></a>выпуск 

 Освобождает предыдущее успешное резервирование сообщения.  
  
```  
virtual void release(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из `message` объект освобожден.  
  
 `_PTarget`  
 Указатель на целевой блок, вызывающий `release` метод.  
  
##  <a name="a-namereleaserefa-releaseref"></a><a name="release_ref"></a>release_ref 

 Освобождает значение счетчика ссылок на это `choice` блок обмена сообщениями.  
  
```  
virtual void release_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на целевой блок, вызывающий этот метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается методом `ITarget` объект, который является, связь которого с этим источником. Блок источника может освободить ресурсы, зарезервированные для целевой блок.  
  
##  <a name="a-namereservea-reserve"></a><a name="reserve"></a>Резерв 

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
 `true`Если сообщение было успешно зарезервированы, `false` в противном случае. Резервирования могут завершаться неудачей по ряду причин, включая следующие: сообщение уже было зарезервировано или принято другим целевым объектом, источник может отклонять резервирования и т. п.  
  
### <a name="remarks"></a>Примечания  
 После вызова метода `reserve`, если он завершается успешно, необходимо вызвать либо `consume` или `release` чтобы принять или высвободить владение сообщением, соответственно.  
  
##  <a name="a-nameunlinktargeta-unlinktarget"></a><a name="unlink_target"></a>unlink_target 

 Удаляет связь целевого блока с это `choice` блок обмена сообщениями.  
  
```  
virtual void unlink_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на `ITarget` блок отсоединиться от этого `choice` блок обмена сообщениями.  
  
##  <a name="a-nameunlinktargetsa-unlinktargets"></a><a name="unlink_targets"></a>unlink_targets 

 Удаляет связь всех целевых объектов из этого `choice` блок обмена сообщениями.  
  
```  
virtual void unlink_targets();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод не вызывается из деструктора, поскольку деструктор для внутреннего `single_assignment` блок будет разрывать связь правильно.  
  
##  <a name="a-namevaluea-value"></a><a name="value"></a>значение 

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
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс JOIN](join-class.md)   
 [Класс single_assignment](single-assignment-class.md)

