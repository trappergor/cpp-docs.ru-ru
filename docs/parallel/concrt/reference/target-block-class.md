---
title: "Класс target_block | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::target_block
dev_langs:
- C++
helpviewer_keywords:
- target_block class
ms.assetid: 3ce181b4-b94a-4894-bf7b-64fc09821f9f
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
ms.openlocfilehash: 0137e95d0d5015fd2e8d18d85388c16ab25a2e9c
ms.lasthandoff: 02/24/2017

---
# <a name="targetblock-class"></a>Класс target_block
Класс `target_block` — это абстрактный базовый класс, который предоставляет основные функции управления соединениями и проверку ошибок только для целевых блоков.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _SourceLinkRegistry::type::source_type>>
class target_block : public ITarget<typename _SourceLinkRegistry::type::source_type>;
```  
  
#### <a name="parameters"></a>Параметры  
 `_SourceLinkRegistry`  
 Реестр ссылок для использования для хранения исходных ссылок.  
  
 `_MessageProcessorType`  
 Тип процессора для обработки сообщений.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`source_iterator`|Тип итератора для `source_link_manager` для этого `target_block` объекта.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор target_block](#ctor)|Создает объект `target_block`.|  
|[~ target_block деструктор](#dtor)|Уничтожает `target_block` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Propagate-метод](#propagate)|Асинхронно передает сообщение из исходного блока данному целевому блоку.|  
|[Send-метод](#send)|Для этого целевого блока синхронно передает сообщение из исходного блока.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[async_send метод](#async_send)|Асинхронно отправляет сообщение для обработки.|  
|[decline_incoming_messages метод](#decline_incoming_messages)|Указывает блоку, что новые сообщения должны быть отклонены.|  
|[enable_batched_processing метод](#enable_batched_processing)|Активирует пакетную обработку для этого блока.|  
|[initialize_target метод](#initialize_target)|Инициализирует базовый объект. В частности `message_processor` объект необходимо инициализировать.|  
|[link_source метод](#link_source)|Связывает указанный целевой блок это `target_block` объекта.|  
|[process_input_messages метод](#process_input_messages)|Обрабатывает сообщения, полученные как входные данные.|  
|[process_message метод](#process_message)|При переопределении в производном классе обрабатывает сообщение, которое ранее было принято данным объектом `target_block`.|  
|[propagate_message метод](#propagate_message)|При переопределении в производном классе этот метод асинхронно передает сообщение от `ISource` блока к этому `target_block` объекта. Он вызывается по `propagate` метод при вызове исходного блока.|  
|[register_filter метод](#register_filter)|Регистрирует метод фильтра, который будет вызван на каждое полученное сообщение.|  
|[remove_sources метод](#remove_sources)|Удаляет связь все источники после ожидания ожидающих операций асинхронной отправки для завершения.|  
|[send_message метод](#send_message)|При переопределении в производном классе этот метод синхронно передает сообщение от `ISource` блока к этому `target_block` объекта. Он вызывается по `send` метод при вызове исходного блока.|  
|[sync_send метод](#sync_send)|Синхронно отправляет сообщение для обработки.|  
|[unlink_source метод](#unlink_source)|Удаляет связь указанного блока источника из этого `target_block` объекта.|  
|[unlink_sources метод](#unlink_sources)|Удаляет связь всех исходных блоков от этого `target_block` объекта. (Переопределяет [ITarget::unlink_sources](itarget-class.md#unlink_sources).)|  
|[wait_for_async_sends метод](#wait_for_async_sends)|Ожидает завершения всех асинхронных операций распространения.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [ITarget](itarget-class.md)  
  
 `target_block`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-nameasyncsenda-asyncsend"></a><a name="async_send"></a>async_send 

 Асинхронно отправляет сообщение для обработки.  
  
```
void async_send(_Inout_opt_ message<_Source_type>* _PMessage);
```  
  
### <a name="parameters"></a>Параметры  
 `_PMessage`  
 Указатель отправляемого сообщения.  
  
##  <a name="a-namedeclineincomingmessagesa-declineincomingmessages"></a><a name="decline_incoming_messages"></a>decline_incoming_messages 

 Указывает блоку, что новые сообщения должны быть отклонены.  
  
```
void decline_incoming_messages();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается деструктором, чтобы убедиться, что новые сообщения отклоняются во время уничтожения.  
  
##  <a name="a-nameenablebatchedprocessinga-enablebatchedprocessing"></a><a name="enable_batched_processing"></a>enable_batched_processing 

 Активирует пакетную обработку для этого блока.  
  
```
void enable_batched_processing();
```  
  
##  <a name="a-nameinitializetargeta-initializetarget"></a><a name="initialize_target"></a>initialize_target 

 Инициализирует базовый объект. В частности `message_processor` объект необходимо инициализировать.  
  
```
void initialize_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `_PScheduler`  
 Планировщик, будет использоваться для планирования задач.  
  
 `_PScheduleGroup`  
 Группа расписаний, которая будет использоваться для планирования задач.  
  
##  <a name="a-namelinksourcea-linksource"></a><a name="link_source"></a>link_source 

 Связывает указанный целевой блок это `target_block` объекта.  
  
```
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Параметры  
 `_PSource`  
 Указатель на `ISource` блок, который должен быть связан.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не должен вызываться непосредственно на `target_block` объект. Блоки должны быть соединены друг с другом с помощью `link_target` метод `ISource` блоков, который будет вызывать `link_source` метод на соответствующий целевой объект.  
  
##  <a name="a-nameprocessinputmessagesa-processinputmessages"></a><a name="process_input_messages"></a>process_input_messages 

 Обрабатывает сообщения, полученные как входные данные.  
  
```
virtual void process_input_messages(_Inout_ message<_Source_type>* _PMessage);
```  
  
### <a name="parameters"></a>Параметры  
 `_PMessage`  
  
##  <a name="a-nameprocessmessagea-processmessage"></a><a name="process_message"></a>process_message 

 При переопределении в производном классе обрабатывает сообщение, которое ранее было принято данным объектом `target_block`.  
  
```
virtual void process_message(message<_Source_type> *);
```  
  
##  <a name="a-namepropagatea-propagate"></a><a name="propagate"></a>распространение 

 Асинхронно передает сообщение из исходного блока данному целевому блоку.  
  
```
virtual message_status propagate(
    _Inout_opt_ message<_Source_type>* _PMessage,
    _Inout_opt_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Параметры  
 `_PMessage`  
 Указатель на объект `message`.  
  
 `_PSource`  
 Указатель на исходный блок, предлагающий сообщение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [message_status](concurrency-namespace-enums.md) указывает на то, что целевой объект решил сделать с сообщением.  
  
### <a name="remarks"></a>Примечания  
 Метод создает [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение, если любой `_PMessage` или `_PSource` параметр `NULL`.  
  
##  <a name="a-namepropagatemessagea-propagatemessage"></a><a name="propagate_message"></a>propagate_message 

 При переопределении в производном классе этот метод асинхронно передает сообщение от `ISource` блока к этому `target_block` объекта. Он вызывается по `propagate` метод при вызове исходного блока.  
  
```
virtual message_status propagate_message(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_PMessage`  
 Указатель на объект `message`.  
  
 `_PSource`  
 Указатель на исходный блок, предлагающий сообщение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [message_status](concurrency-namespace-enums.md) указывает на то, что целевой объект решил сделать с сообщением.  
  
##  <a name="a-nameregisterfiltera-registerfilter"></a><a name="register_filter"></a>register_filter 

 Регистрирует метод фильтра, который будет вызван на каждое полученное сообщение.  
  
```
void register_filter(filter_method const& _Filter);
```  
  
### <a name="parameters"></a>Параметры  
 `_Filter`  
 Метод фильтра.  
  
##  <a name="a-nameremovesourcesa-removesources"></a><a name="remove_sources"></a>remove_sources 

 Удаляет связь все источники после ожидания ожидающих операций асинхронной отправки для завершения.  
  
```
void remove_sources();
```  
  
### <a name="remarks"></a>Примечания  
 Все целевые блоки должны вызывать данную процедуру для удаления источников в их деструкторе.  
  
##  <a name="a-namesenda-send"></a><a name="send"></a>Отправить 

 Для этого целевого блока синхронно передает сообщение из исходного блока.  
  
```
virtual message_status send(
    _Inout_ message<_Source_type>* _PMessage,
    _Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Параметры  
 `_PMessage`  
 Указатель на объект `message`.  
  
 `_PSource`  
 Указатель на исходный блок, предлагающий сообщение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [message_status](concurrency-namespace-enums.md) указывает на то, что целевой объект решил сделать с сообщением.  
  
### <a name="remarks"></a>Примечания  
 Метод создает [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение, если любой `_PMessage` или `_PSource` параметр `NULL`.  
  
 С помощью `send` метод вне инициации сообщения и для распространения сообщений внутри сети небезопасно и может привести к взаимоблокировке.  
  
 Если `send` возвращает сообщение либо уже было принято и передано в блок целевой или было отклонено целевым объектом.  
  
##  <a name="a-namesendmessagea-sendmessage"></a><a name="send_message"></a>send_message 

 При переопределении в производном классе этот метод синхронно передает сообщение от `ISource` блока к этому `target_block` объекта. Он вызывается по `send` метод при вызове исходного блока.  
  
```
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [message_status](concurrency-namespace-enums.md) указывает на то, что целевой объект решил сделать с сообщением.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот блок возвращает `declined` Если не переопределено в производном классе.  
  
##  <a name="a-namesyncsenda-syncsend"></a><a name="sync_send"></a>sync_send 

 Синхронно отправляет сообщение для обработки.  
  
```
void sync_send(_Inout_opt_ message<_Source_type>* _PMessage);
```  
  
### <a name="parameters"></a>Параметры  
 `_PMessage`  
 Указатель отправляемого сообщения.  
  
##  <a name="a-namectora-targetblock"></a><a name="ctor"></a>target_block 

 Создает объект `target_block`.  
  
```
target_block();
```  
  
##  <a name="a-namedtora-targetblock"></a><a name="dtor"></a>~ target_block 

 Уничтожает `target_block` объекта.  
  
```
virtual ~target_block();
```  
  
##  <a name="a-nameunlinksourcea-unlinksource"></a><a name="unlink_source"></a>unlink_source 

 Удаляет связь указанного блока источника из этого `target_block` объекта.  
  
```
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Параметры  
 `_PSource`  
 Указатель на `ISource` блок, который должен быть удалена.  
  
##  <a name="a-nameunlinksourcesa-unlinksources"></a><a name="unlink_sources"></a>unlink_sources 

 Удаляет связь всех исходных блоков от этого `target_block` объекта.  
  
```
virtual void unlink_sources();
```  
  
##  <a name="a-namewaitforasyncsendsa-waitforasyncsends"></a><a name="wait_for_async_sends"></a>wait_for_async_sends 

 Ожидает завершения всех асинхронных операций распространения.  
  
```
void wait_for_async_sends();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется деструкторами блока сообщений, чтобы убедиться, что все асинхронные операции имели время для окончания перед удалением блока.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс ITarget](itarget-class.md)

