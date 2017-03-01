---
title: "Класс source_block | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::source_block
dev_langs:
- C++
helpviewer_keywords:
- source_block class
ms.assetid: fbdd4146-e8d0-42e8-b714-fe633f69ffbf
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
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 7d459d03153e95b779b8f8b19d2a68602b33acf8
ms.lasthandoff: 02/24/2017

---
# <a name="sourceblock-class"></a>Класс source_block
Класс `source_block` — это абстрактный базовый класс только для блоков источника. Класс предоставляет основные функции управления соединениями, а также проверки распространенных ошибок.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class _TargetLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class source_block : public ISource<typename _TargetLinkRegistry::type::type>;
```  
  
#### <a name="parameters"></a>Параметры  
 `_TargetLinkRegistry`  
 Реестр ссылок для использования для хранения целевых ссылок.  
  
 `_MessageProcessorType`  
 Тип процессора для обработки сообщений.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`target_iterator`|Итератор для прохода подключенных целевых объектов.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор source_block](#ctor)|Создает объект `source_block`.|  
|[~ source_block деструктор](#dtor)|Уничтожает `source_block` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Accept-метод](#accept)|Принимает сообщение, предложенное это `source_block` объекта, передавая владение вызывающему объекту.|  
|[acquire_ref метод](#acquire_ref)|Получает значение счетчика ссылок на это `source_block` объекта, чтобы предотвратить удаление.|  
|[consume-метод](#consume)|Потребляет сообщение, ранее предложенное это `source_block` объекта и успешно зарезервированное целевым объектом, передавая владение вызывающему объекту.|  
|[Метод link_target](#link_target)|Это связывает целевой блок `source_block` объекта.|  
|[Release-метод](#release)|Освобождает предыдущее успешное резервирование сообщения.|  
|[release_ref метод](#release_ref)|Освобождает значение счетчика ссылок на это `source_block` объекта.|  
|[reserve-метод](#reserve)|Резервирует сообщение, которое было предложено это `source_block` объекта.|  
|[unlink_target метод](#unlink_target)|Удаляет связь целевого блока с это `source_block` объекта.|  
|[unlink_targets метод](#unlink_targets)|Удаляет связь всех целевых блоков от этого `source_block` объекта. (Переопределяет [ISource::unlink_targets](isource-class.md#unlink_targets).)|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[accept_message метод](#accept_message)|При переопределении в производном классе, принимает сообщение, предложенное источником. Блоки сообщений должны переопределять этот метод для проверки `_MsgId` и возвращает сообщение.|  
|[Метод async_send](#async_send)|Асинхронно ставит в очередь сообщения и запускает задачу распространения, если это еще не сделано|  
|[consume_message метод](#consume_message)|При переопределении в производном классе получает сообщение, которое ранее было зарезервировано.|  
|[enable_batched_processing метод](#enable_batched_processing)|Активирует пакетную обработку для этого блока.|  
|[initialize_source метод](#initialize_source)|Инициализирует `message_propagator` в рамках этого `source_block`.|  
|[link_target_notification метод](#link_target_notification)|Обратный вызов, который уведомляет, что новая цель связана к этому `source_block` объекта.|  
|[process_input_messages метод](#process_input_messages)|Обработка входных сообщений. Подходит только для блоков распространения, производных от source_block.|  
|[propagate_output_messages метод](#propagate_output_messages)|Распространение сообщений в целевые объекты.|  
|[propagate_to_any_targets метод](#propagate_to_any_targets)|При переопределении в производном классе распространяет данное сообщения для любой или все связанные целевые объекты. Это основной способ распространения подпрограммы для блоков сообщений.|  
|[release_message метод](#release_message)|При переопределении в производном классе освобождает предыдущее резервирование сообщения.|  
|[remove_targets метод](#remove_targets)|Удаляет все целевые ссылки для этого исходного блока. Должен быть вызван из деструктора.|  
|[reserve_message метод](#reserve_message)|При переопределении в производном классе резервирует сообщение, которое было предложено это `source_block` объекта.|  
|[resume_propagation метод](#resume_propagation)|При переопределении в производном классе возобновляет распространение после выпуска резервирования.|  
|[sync_send метод](#sync_send)|Синхронно ставит в очередь сообщения и запускает задачу распространения, если это еще не сделано.|  
|[unlink_target_notification метод](#unlink_target_notification)|Обратный вызов, который уведомляет о том, что целевой объект была удалена из этого `source_block` объекта.|  
|[wait_for_outstanding_async_sends метод](#wait_for_outstanding_async_sends)|Ожидает завершения всех асинхронных операций распространения. Ожидание прокрутки определенного распространителя используется в деструкторах блоков сообщений, чтобы убедиться в том, что все асинхронные распространители имеют достаточно времени для окончания перед удалением блока.|  
  
## <a name="remarks"></a>Примечания  
 Сообщений блоки должны быть производными от этого блока, чтобы воспользоваться преимуществами управление ссылками и синхронизации, предоставленные этим классом.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [ISource](isource-class.md)  
  
 `source_block`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-nameaccepta-accept"></a><a name="accept"></a>принять 

 Принимает сообщение, предложенное это `source_block` объекта, передавая владение вызывающему объекту.  
  
```
virtual message<_Target_type>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из предложенных `message` объекта.  
  
 `_PTarget`  
 Указатель на целевой блок, вызывающий `accept` метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `message` объект, вызывающий теперь принадлежит.  
  
### <a name="remarks"></a>Примечания  
 Метод создает [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение при параметре `_PTarget` — `NULL`.  
  
 `accept` Метод вызывается целевой объект, пока сообщение предлагается это `ISource` блок. Сообщение указатель, возвращенный может отличаться от того, переданные в `propagate` метод `ITarget` блокировать, если этот источник решает создать копию сообщения.  
  
##  <a name="a-nameacceptmessagea-acceptmessage"></a><a name="accept_message"></a>accept_message 

 При переопределении в производном классе, принимает сообщение, предложенное источником. Блоки сообщений должны переопределять этот метод для проверки `_MsgId` и возвращает сообщение.  
  
```
virtual message<_Target_type>* accept_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 Идентификатор объекта среды выполнения `message` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на сообщение, которое теперь принадлежит вызывающей стороне.  
  
### <a name="remarks"></a>Примечания  
 Для передачи владения исходный указатель сообщения должно быть возвращено. Для поддержания владения копию полезных данных сообщения необходимо сделать и вернуть.  
  
##  <a name="a-nameacquirerefa-acquireref"></a><a name="acquire_ref"></a>acquire_ref 

 Получает значение счетчика ссылок на это `source_block` объекта, чтобы предотвратить удаление.  
  
```
virtual void acquire_ref(_Inout_ ITarget<_Target_type> *);
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается методом `ITarget` объекта, который связан с этим источником во время `link_target` метод.  
  
##  <a name="a-nameasyncsenda-asyncsend"></a><a name="async_send"></a>async_send 

 Асинхронно ставит в очередь сообщения и запускает задачу распространения, если это еще не сделано  
  
```
virtual void async_send(_Inout_opt_ message<_Target_type>* _Msg);
```  
  
### <a name="parameters"></a>Параметры  
 `_Msg`  
 Указатель на `message` объект для асинхронной передачи.  
  
##  <a name="a-nameconsumea-consume"></a><a name="consume"></a>Использование 

 Потребляет сообщение, ранее предложенное это `source_block` объекта и успешно зарезервированное целевым объектом, передавая владение вызывающему объекту.  
  
```
virtual message<_Target_type>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Зарезервированных `message` объекта.  
  
 `_PTarget`  
 Указатель на целевой блок, вызывающий `consume` метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `message` объект, вызывающий теперь принадлежит.  
  
### <a name="remarks"></a>Примечания  
 Метод создает [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение при параметре `_PTarget` — `NULL`.  
  
 Метод создает [bad_target](bad-target-class.md) исключение если параметр `_PTarget` не представляет целевой объект, который называется `reserve`.  
  
 `consume` Метод аналогичен `accept`, но всегда должно начинаться с помощью вызова `reserve` , возвращается `true`.  
  
##  <a name="a-nameconsumemessagea-consumemessage"></a><a name="consume_message"></a>consume_message 

 При переопределении в производном классе получает сообщение, которое ранее было зарезервировано.  
  
```
virtual message<_Target_type>* consume_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из `message` объекта использованное.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на сообщение, которое теперь принадлежит вызывающей стороне.  
  
### <a name="remarks"></a>Примечания  
 Аналогично `accept`, но всегда предшествует вызов `reserve`.  
  
##  <a name="a-nameenablebatchedprocessinga-enablebatchedprocessing"></a><a name="enable_batched_processing"></a>enable_batched_processing 

 Активирует пакетную обработку для этого блока.  
  
```
void enable_batched_processing();
```  
  
##  <a name="a-nameinitializesourcea-initializesource"></a><a name="initialize_source"></a>initialize_source 

 Инициализирует `message_propagator` в рамках этого `source_block`.  
  
```
void initialize_source(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `_PScheduler`  
 Планировщик, будет использоваться для планирования задач.  
  
 `_PScheduleGroup`  
 Группа расписаний, которая будет использоваться для планирования задач.  
  
##  <a name="a-namelinktargeta-linktarget"></a><a name="link_target"></a>link_target 

 Это связывает целевой блок `source_block` объекта.  
  
```
virtual void link_target(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на `ITarget` блок, чтобы создать ссылку на этот `source_block` объекта.  
  
### <a name="remarks"></a>Примечания  
 Метод создает [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение при параметре `_PTarget` — `NULL`.  
  
##  <a name="a-namelinktargetnotificationa-linktargetnotification"></a><a name="link_target_notification"></a>link_target_notification 

 Обратный вызов, который уведомляет, что новая цель связана к этому `source_block` объекта.  
  
```
virtual void link_target_notification(_Inout_ ITarget<_Target_type> *);
```  
  
##  <a name="a-nameprocessinputmessagesa-processinputmessages"></a><a name="process_input_messages"></a>process_input_messages 

 Обработка входных сообщений. Подходит только для блоков распространения, производных от source_block.  
  
```
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```  
  
### <a name="parameters"></a>Параметры  
 `_PMessage`  
  
##  <a name="a-namepropagateoutputmessagesa-propagateoutputmessages"></a><a name="propagate_output_messages"></a>propagate_output_messages 

 Распространение сообщений в целевые объекты.  
  
```
virtual void propagate_output_messages();
```  
  
##  <a name="a-namepropagatetoanytargetsa-propagatetoanytargets"></a><a name="propagate_to_any_targets"></a>propagate_to_any_targets 

 При переопределении в производном классе распространяет данное сообщения для любой или все связанные целевые объекты. Это основной способ распространения подпрограммы для блоков сообщений.  
  
```
virtual void propagate_to_any_targets(_Inout_opt_ message<_Target_type>* _PMessage);
```  
  
### <a name="parameters"></a>Параметры  
 `_PMessage`  
 Указатель на сообщение, которое будет распространяться.  
  
##  <a name="a-namereleasea-release"></a><a name="release"></a>выпуск 

 Освобождает предыдущее успешное резервирование сообщения.  
  
```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Зарезервированных `message` объекта.  
  
 `_PTarget`  
 Указатель на целевой блок, вызывающий `release` метод.  
  
### <a name="remarks"></a>Примечания  
 Метод создает [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение при параметре `_PTarget` — `NULL`.  
  
 Метод создает [bad_target](bad-target-class.md) исключение если параметр `_PTarget` не представляет целевой объект, который называется `reserve`.  
  
##  <a name="a-namereleasemessagea-releasemessage"></a><a name="release_message"></a>release_message 

 При переопределении в производном классе освобождает предыдущее резервирование сообщения.  
  
```
virtual void release_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из `message` объект освобожден.  
  
##  <a name="a-namereleaserefa-releaseref"></a><a name="release_ref"></a>release_ref 

 Освобождает значение счетчика ссылок на это `source_block` объекта.  
  
```
virtual void release_ref(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на целевой блок, вызывающий этот метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается методом `ITarget` объект, который является, связь которого с этим источником. Блок источника может освободить ресурсы, зарезервированные для целевой блок.  
  
##  <a name="a-nameremovetargetsa-removetargets"></a><a name="remove_targets"></a>remove_targets 

 Удаляет все целевые ссылки для этого исходного блока. Должен быть вызван из деструктора.  
  
```
void remove_targets();
```  
  
##  <a name="a-namereservea-reserve"></a><a name="reserve"></a>Резерв 

 Резервирует сообщение, которое было предложено это `source_block` объекта.  
  
```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из предложенных `message` объекта.  
  
 `_PTarget`  
 Указатель на целевой блок, вызывающий `reserve` метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если сообщение было успешно зарезервированы, `false` в противном случае. Резервирования могут завершаться неудачей по ряду причин, включая следующие: сообщение уже было зарезервировано или принято другим целевым объектом, источник может отклонять резервирования и т. п.  
  
### <a name="remarks"></a>Примечания  
 Метод создает [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение при параметре `_PTarget` — `NULL`.  
  
 После вызова метода `reserve`, если он завершается успешно, необходимо вызвать либо `consume` или `release` чтобы принять или высвободить владение сообщением, соответственно.  
  
##  <a name="a-namereservemessagea-reservemessage"></a><a name="reserve_message"></a>reserve_message 

 При переопределении в производном классе резервирует сообщение, которое было предложено это `source_block` объекта.  
  
```
virtual bool reserve_message(runtime_object_identity _MsgId) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из `message` объекта резервируются.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если сообщение было успешно зарезервированы, `false` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 После `reserve` вызывается, если она возвращает `true`, либо `consume` или `release` необходимо вызвать, чтобы принять или высвободить владение сообщением.  
  
##  <a name="a-nameresumepropagationa-resumepropagation"></a><a name="resume_propagation"></a>resume_propagation 

 При переопределении в производном классе возобновляет распространение после выпуска резервирования.  
  
```
virtual void resume_propagation() = 0;
```  
  
##  <a name="a-namectora-sourceblock"></a><a name="ctor"></a>source_block 

 Создает объект `source_block`.  
  
```
source_block();
```  
  
##  <a name="a-namedtora-sourceblock"></a><a name="dtor"></a>~ source_block 

 Уничтожает `source_block` объекта.  
  
```
virtual ~source_block();
```  
  
##  <a name="a-namesyncsenda-syncsend"></a><a name="sync_send"></a>sync_send 

 Синхронно ставит в очередь сообщения и запускает задачу распространения, если это еще не сделано.  
  
```
virtual void sync_send(_Inout_opt_ message<_Target_type>* _Msg);
```  
  
### <a name="parameters"></a>Параметры  
 `_Msg`  
 Указатель на `message` объект для синхронной отправки.  
  
##  <a name="a-nameunlinktargeta-unlinktarget"></a><a name="unlink_target"></a>unlink_target 

 Удаляет связь целевого блока с это `source_block` объекта.  
  
```
virtual void unlink_target(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на `ITarget` блок отсоединиться от этого `source_block` объекта.  
  
### <a name="remarks"></a>Примечания  
 Метод создает [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение при параметре `_PTarget` — `NULL`.  
  
##  <a name="a-nameunlinktargetnotificationa-unlinktargetnotification"></a><a name="unlink_target_notification"></a>unlink_target_notification 

 Обратный вызов, который уведомляет о том, что целевой объект была удалена из этого `source_block` объекта.  
  
```
virtual void unlink_target_notification(_Inout_ ITarget<_Target_type>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 `ITarget` Блок, была удалена.  
  
##  <a name="a-nameunlinktargetsa-unlinktargets"></a><a name="unlink_targets"></a>unlink_targets 

 Удаляет связь всех целевых блоков от этого `source_block` объекта.  
  
```
virtual void unlink_targets();
```  
  
##  <a name="a-namewaitforoutstandingasyncsendsa-waitforoutstandingasyncsends"></a><a name="wait_for_outstanding_async_sends"></a>wait_for_outstanding_async_sends 

 Ожидает завершения всех асинхронных операций распространения. Ожидание прокрутки определенного распространителя используется в деструкторах блоков сообщений, чтобы убедиться в том, что все асинхронные распространители имеют достаточно времени для окончания перед удалением блока.  
  
```
void wait_for_outstanding_async_sends();
```  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс ISource](isource-class.md)

