---
title: "Класс unbounded_buffer | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- unbounded_buffer
dev_langs:
- C++
ms.assetid: 6b1a939a-1819-4385-b1d8-708f83d4ec47
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 561f2eea7a2eb19d8cc0162df8bf659f22da1065
ms.lasthandoff: 02/24/2017

---


Блок обмена сообщениями `unbounded_buffer` — это упорядоченный блок `propagator_block` с несколькими целями и несколькими источниками, который может хранить неограниченное число сообщений.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<  
   class             _Type  
>  
class unbounded_buffer : public propagator_block<multi_link_registry<ITarget<            _Type>>, multi_link_registry<ISource<            _Type>>>;  
```  
  
#### <a name="parameters"></a>Параметры  
 `_Type`  
 Тип полезных данных сохраненных и распространенных буфером сообщений.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[unbounded_buffer конструктор](#ctor)|Перегружен. Создает `unbounded_buffer` блок обмена сообщениями.|  
|[~ unbounded_buffer деструктор](#dtor)|Уничтожает `unbounded_buffer` блок обмена сообщениями.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[dequeue-метод](#dequeue)|Удаляет элемент из `unbounded_buffer` блок обмена сообщениями.|  
|[Метод постановки в очередь](#enqueue)|Добавляет элемент в `unbounded_buffer` блок обмена сообщениями.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[accept_message метод](#accept_message)|Принимает сообщение, предложенное это `unbounded_buffer` блок сообщений, передавая владение вызывающему объекту.|  
|[consume_message метод](#consume_message)|Потребляет сообщение, ранее предложенное `unbounded_buffer` блок обмена сообщениями и зарезервированное целевым объектом, передавая владение вызывающему объекту.|  
|[link_target_notification метод](#link_target_notification)|Обратный вызов, который уведомляет, что новая цель связана к этому `unbounded_buffer` блок обмена сообщениями.|  
|[process_input_messages метод](#process_input_messages)|Окружение `message``_PMessage` в этом `unbounded_buffer` блок сообщений и пытается предложить его ко всем связанным целевым объектам.|  
|[propagate_message метод](#propagate_message)|Асинхронно передает сообщение из `ISource` блока к этому `unbounded_buffer` блок обмена сообщениями. Он вызывается по `propagate` метод при вызове исходного блока.|  
|[propagate_output_messages метод](#propagate_output_messages)|Окружение `message``_PMessage` в этом `unbounded_buffer` блок сообщений и пытается предложить его ко всем связанным целевым объектам. (Переопределяет [source_block::propagate_output_messages](source-block-class.md#propagate_output_messages).)|  
|[release_message метод](#release_message)|Освобождает предыдущее резервирование сообщения. (Переопределяет [source_block::release_message](source-block-class.md#release_message).)|  
|[reserve_message метод](#reserve_message)|Резервирует сообщение, которое было предложено это `unbounded_buffer` блок обмена сообщениями. (Переопределяет [source_block::reserve_message](source-block-class.md#reserve_message).)|  
|[resume_propagation метод](#resume_propagation)|Возобновляет распространение после выпуска резервирования. (Переопределяет [source_block::resume_propagation](source-block-class.md#resume_propagation).)|  
|[send_message метод](#send_message)|Синхронно передает сообщение от `ISource` блока к этому `unbounded_buffer` блок обмена сообщениями. Он вызывается по `send` метод при вызове исходного блока.|  
|[supports_anonymous_source метод](#supports_anonymous_source)|Переопределяет метод `supports_anonymous_source`, чтобы указать, что данный блок может принимать сообщения, предоставляемые ему несвязанным источником. (Переопределяет [ITarget::supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|  

 Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [ISource](isource-class.md)  
  
 [ITarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 [propagator_block](propagator-block-class.md)  
  
 `unbounded_buffer`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-nameacceptmessagea-acceptmessage"></a><a name="accept_message"></a>accept_message 

 Принимает сообщение, предложенное это `unbounded_buffer` блок сообщений, передавая владение вызывающему объекту.  
  
```  
virtual message<_Type> * accept_message(  
   runtime_object_identity                 _MsgId  
);  
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из предложенных `message` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `message` объект, вызывающий теперь принадлежит.  
  
##  <a name="a-nameconsumemessagea-consumemessage"></a><a name="consume_message"></a>consume_message 

 Потребляет сообщение, ранее предложенное `unbounded_buffer` блок обмена сообщениями и зарезервированное целевым объектом, передавая владение вызывающему объекту.  
  
```  
virtual message<_Type> * consume_message(  
   runtime_object_identity                 _MsgId  
);  
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из `message` объекта использованное.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `message` объект, вызывающий теперь принадлежит.  
  
### <a name="remarks"></a>Примечания  
 Аналогично `accept`, но всегда предшествует вызов `reserve`.  
  
##  <a name="a-namedequeuea-dequeue"></a><a name="dequeue"></a>Удаление из очереди 

 Удаляет элемент из `unbounded_buffer` блок обмена сообщениями.  
  
```  
_Type dequeue();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Полезные данные сообщения, удалены из `unbounded_buffer`.  
  
##  <a name="a-nameenqueuea-enqueue"></a><a name="enqueue"></a>Постановка в очередь 

 Добавляет элемент в `unbounded_buffer` блок обмена сообщениями.  
  
```  
bool enqueue(  
   _Type const&                 _Item  
);  
```  
  
### <a name="parameters"></a>Параметры  
 `_Item`  
 Добавляемый элемент.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если элемент был принят, `false` в противном случае.  
  
##  <a name="a-namelinktargetnotificationa-linktargetnotification"></a><a name="link_target_notification"></a>link_target_notification 

 Обратный вызов, который уведомляет, что новая цель связана к этому `unbounded_buffer` блок обмена сообщениями.  
  
```  
virtual void link_target_notification(  
   _Inout_ ITarget<_Type> *                 _PTarget  
);  
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на только что привязанный целевой объект.  
  
##  <a name="a-namepropagatemessagea-propagatemessage"></a><a name="propagate_message"></a>propagate_message 

 Асинхронно передает сообщение из `ISource` блока к этому `unbounded_buffer` блок обмена сообщениями. Он вызывается по `propagate` метод при вызове исходного блока.  
  
```  
virtual message_status propagate_message(  
   _Inout_ message<_Type> *                 _PMessage,  
   _Inout_ ISource<_Type> *                 _PSource  
);  
```  
  
### <a name="parameters"></a>Параметры  
 `_PMessage`  
 Указатель на объект `message`.  
  
 `_PSource`  
 Указатель на исходный блок, предлагающий сообщение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [message_status](concurrency-namespace-enums.md#message_status) указывает на то, что целевой объект решил сделать с сообщением.  
  
##  <a name="a-namepropagateoutputmessagesa-propagateoutputmessages"></a><a name="propagate_output_messages"></a>propagate_output_messages 

 Окружение `message``_PMessage` в этом `unbounded_buffer` блок сообщений и пытается предложить его ко всем связанным целевым объектам.  
  
```  
virtual void propagate_output_messages();  
```  
  
### <a name="remarks"></a>Примечания  
 Если другое сообщение уже впереди этого в `unbounded_buffer`, распространение связанным целевым объектам не произойдет, пока не приняты или потреблены все предыдущие сообщения. Первый связанный целевой объект, чтобы успешно `accept` или `consume` сообщение становится владельцем и нет других целевых объектов можно получить сообщение.  
  
##  <a name="a-nameprocessinputmessagesa-processinputmessages"></a><a name="process_input_messages"></a>process_input_messages 

 Окружение `message``_PMessage` в этом `unbounded_buffer` блок сообщений и пытается предложить его ко всем связанным целевым объектам.  
  
```  
virtual void process_input_messages(  
   _Inout_ message<_Type> *                 _PMessage  
);  
```  
  
### <a name="parameters"></a>Параметры  
 `_PMessage`  
  
##  <a name="a-namereleasemessagea-releasemessage"></a><a name="release_message"></a>release_message 

 Освобождает предыдущее резервирование сообщения.  
  
```  
virtual void release_message(  
   runtime_object_identity                 _MsgId  
);  
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из `message` объект освобожден.  
  
##  <a name="a-namereservemessagea-reservemessage"></a><a name="reserve_message"></a>reserve_message 

 Резервирует сообщение, которое было предложено это `unbounded_buffer` блок обмена сообщениями.  
  
```  
virtual bool reserve_message(  
   runtime_object_identity                 _MsgId  
);  
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из `message` объекта резервируются.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если сообщение было успешно зарезервированы, `false` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 После `reserve` вызывается, если она возвращает `true`, либо `consume` или `release` необходимо вызвать, чтобы принять или высвободить владение сообщением.  
  
##  <a name="a-nameresumepropagationa-resumepropagation"></a><a name="resume_propagation"></a>resume_propagation 

 Возобновляет распространение после выпуска резервирования.  
  
```  
virtual void resume_propagation();  
```  
  
##  <a name="a-namesendmessagea-sendmessage"></a><a name="send_message"></a>send_message 

 Синхронно передает сообщение от `ISource` блока к этому `unbounded_buffer` блок обмена сообщениями. Он вызывается по `send` метод при вызове исходного блока.  
  
```  
virtual message_status send_message(  
   _Inout_ message<_Type> *                 _PMessage,  
   _Inout_ ISource<_Type> *                 _PSource  
);  
```  
  
### <a name="parameters"></a>Параметры  
 `_PMessage`  
 Указатель на объект `message`.  
  
 `_PSource`  
 Указатель на исходный блок, предлагающий сообщение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [message_status](concurrency-namespace-enums.md#message_status) указывает на то, что целевой объект решил сделать с сообщением.  
  
##  <a name="a-namesupportsanonymoussourcea-supportsanonymoussource"></a><a name="supports_anonymous_source"></a>supports_anonymous_source 

 Переопределяет метод `supports_anonymous_source`, чтобы указать, что данный блок может принимать сообщения, предоставляемые ему несвязанным источником.  
  
```  
virtual bool supports_anonymous_source();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, поскольку блок не откладывает предоставляемые сообщения.  
  
##  <a name="a-namectora-unboundedbuffer"></a><a name="ctor"></a>unbounded_buffer 

 Создает `unbounded_buffer` блок обмена сообщениями.  
  
```  
unbounded_buffer();  
  
unbounded_buffer(  
   filter_method const&                 _Filter  
);  
  
unbounded_buffer(  
   Scheduler&                 _PScheduler  
);  
  
unbounded_buffer(  
   Scheduler&                 _PScheduler,  
   filter_method const&                 _Filter  
);  
  
unbounded_buffer(  
   ScheduleGroup&                 _PScheduleGroup  
);  
  
unbounded_buffer(  
   ScheduleGroup&                 _PScheduleGroup,  
   filter_method const&                 _Filter  
);  
```  
  
### <a name="parameters"></a>Параметры  
 `_Filter`  
 Функции фильтра, который определяет, следует ли принять предложенное сообщения.  
  
 `_PScheduler`  
 `Scheduler` Объекта, в течение которого задача распространения `unbounded_buffer` запланирована блок обмена сообщениями.  
  
 `_PScheduleGroup`  
 `ScheduleGroup` Объекта, в течение которого задача распространения `unbounded_buffer` запланирована блок обмена сообщениями. Используемый объект `Scheduler` подразумевается группой расписаний.  
  
### <a name="remarks"></a>Примечания  
 Среда выполнения использует планировщик по умолчанию, если вы не указали параметры `_PScheduler` или `_PScheduleGroup` .  
  
 Тип `filter_method` является функтор подписью `bool (_Type const &)` которого вызывается этим `unbounded_buffer` блок сообщений, чтобы определить ли он должен принять предложенное сообщение.  
  
##  <a name="a-namedtora-unboundedbuffer"></a><a name="dtor"></a>~ unbounded_buffer 

 Уничтожает `unbounded_buffer` блок обмена сообщениями.  
  
```  
~unbounded_buffer();  
```  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс overwrite_buffer](overwrite-buffer-class.md)   
 [Класс single_assignment](single-assignment-class.md)



