---
title: "Класс ordered_message_processor | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::ordered_message_processor
dev_langs:
- C++
helpviewer_keywords:
- ordered_message_processor class
ms.assetid: 787adfb7-7f79-4a70-864a-80e3b64088cd
caps.latest.revision: 17
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
ms.openlocfilehash: a9653c8eb5f05e56fd7812d334575e62dc101d63
ms.lasthandoff: 02/24/2017

---
# <a name="orderedmessageprocessor-class"></a>Класс ordered_message_processor
Класс `ordered_message_processor` представляет собой `message_processor`, который позволяет блокам обмена сообщениями обрабатывать сообщения в том порядке, в котором они их получают.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>
class ordered_message_processor : public message_processor<T>;
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип полезных данных сообщений, обработанных обработчиком.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`type`|Псевдоним для `T`.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор ordered_message_processor](#ctor)|Создает объект `ordered_message_processor`.|  
|[~ ordered_message_processor деструктор](#dtor)|Уничтожает `ordered_message_processor` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод async_send](#async_send)|Асинхронно ставит в очередь сообщения и запускает задачу обработки, если это еще не сделано. (Переопределяет [message_processor::async_send](message-processor-class.md#async_send).)|  
|[Метод Initialize](#initialize)|Инициализирует `ordered_message_processor` объект с соответствующей обратного вызова функцией, планировщик и расписание группы.|  
|[initialize_batched_processing метод](#initialize_batched_processing)|Инициализация обработки пакетных сообщений|  
|[sync_send метод](#sync_send)|Синхронно ставит в очередь сообщения и запускает задачу обработки, если это еще не сделано. (Переопределяет [message_processor::sync_send](message-processor-class.md#sync_send).)|  
|[wait-метод](#wait)|Ожидание прокрутки определенного процессора, используемое в деструкторах блоков сообщений, чтобы убедиться в том, что все задачи асинхронной обработки имеют достаточно времени для окончания перед удалением блока. (Переопределяет [message_processor::wait](message-processor-class.md#wait).)|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[process_incoming_message метод](#process_incoming_message)|Функция обработки, которая вызывается асинхронно. Он удаляет сообщения из очереди и начинает обработку их. (Переопределяет [message_processor::process_incoming_message](message-processor-class.md#process_incoming_message).)|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [message_processor](message-processor-class.md)  
  
 `ordered_message_processor`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-nameasyncsenda-asyncsend"></a><a name="async_send"></a>async_send 

 Асинхронно ставит в очередь сообщения и запускает задачу обработки, если это еще не сделано.  
  
```
virtual void async_send(_Inout_opt_ message<T>* _Msg);
```  
  
### <a name="parameters"></a>Параметры  
 `_Msg`  
 Указатель на сообщение.  
  
##  <a name="a-nameinitializea-initialize"></a><a name="initialize"></a>Инициализация 

 Инициализирует `ordered_message_processor` объект с соответствующей обратного вызова функцией, планировщик и расписание группы.  
  
```
void initialize(
    _Inout_opt_ Scheduler* _PScheduler,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup,
    _Handler_method const& _Handler);
```  
  
### <a name="parameters"></a>Параметры  
 `_PScheduler`  
 Указатель на планировщик, будет использоваться для планирования простых задач.  
  
 `_PScheduleGroup`  
 Указатель на группу расписаний, которая будет использоваться для планирования простых задач.  
  
 `_Handler`  
 Функтор обработчик вызывается во время обратного вызова.  
  
##  <a name="a-nameinitializebatchedprocessinga-initializebatchedprocessing"></a><a name="initialize_batched_processing"></a>initialize_batched_processing 

 Инициализация обработки пакетных сообщений  
  
```
virtual void initialize_batched_processing(
    _Handler_method const& _Processor,
    _Propagator_method const& _Propagator);
```  
  
### <a name="parameters"></a>Параметры  
 `_Processor`  
 Процессор функтор вызывается во время обратного вызова.  
  
 `_Propagator`  
 Распространитель функтор вызывается во время обратного вызова.  
  
##  <a name="a-namectora-orderedmessageprocessor"></a><a name="ctor"></a>ordered_message_processor 

 Создает объект `ordered_message_processor`.  
  
```
ordered_message_processor();
```  
  
### <a name="remarks"></a>Примечания  
 Это `ordered_message_processor` асинхронный или синхронный обработчики, пока не будет планировать `initialize` вызывается функция.  
  
##  <a name="a-namedtora-orderedmessageprocessor"></a><a name="dtor"></a>~ ordered_message_processor 

 Уничтожает `ordered_message_processor` объекта.  
  
```
virtual ~ordered_message_processor();
```  
  
### <a name="remarks"></a>Примечания  
 Ожиданий для всех ожидающих асинхронных операций перед удалением процессора.  
  
##  <a name="a-nameprocessincomingmessagea-processincomingmessage"></a><a name="process_incoming_message"></a>process_incoming_message 

 Функция обработки, которая вызывается асинхронно. Он удаляет сообщения из очереди и начинает обработку их.  
  
```
virtual void process_incoming_message();
```  
  
##  <a name="a-namesyncsenda-syncsend"></a><a name="sync_send"></a>sync_send 

 Синхронно ставит в очередь сообщения и запускает задачу обработки, если это еще не сделано.  
  
```
virtual void sync_send(_Inout_opt_ message<T>* _Msg);
```  
  
### <a name="parameters"></a>Параметры  
 `_Msg`  
 Указатель на сообщение.  
  
##  <a name="a-namewaita-wait"></a><a name="wait"></a>Ожидание 

 Ожидание прокрутки определенного процессора, используемое в деструкторах блоков сообщений, чтобы убедиться в том, что все задачи асинхронной обработки имеют достаточно времени для окончания перед удалением блока.  
  
```
virtual void wait();
```  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)

