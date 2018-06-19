---
title: Класс target_block | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- target_block
- AGENTS/concurrency::target_block
- AGENTS/concurrency::target_block::target_block
- AGENTS/concurrency::target_block::propagate
- AGENTS/concurrency::target_block::send
- AGENTS/concurrency::target_block::async_send
- AGENTS/concurrency::target_block::decline_incoming_messages
- AGENTS/concurrency::target_block::enable_batched_processing
- AGENTS/concurrency::target_block::initialize_target
- AGENTS/concurrency::target_block::link_source
- AGENTS/concurrency::target_block::process_input_messages
- AGENTS/concurrency::target_block::process_message
- AGENTS/concurrency::target_block::propagate_message
- AGENTS/concurrency::target_block::register_filter
- AGENTS/concurrency::target_block::remove_sources
- AGENTS/concurrency::target_block::send_message
- AGENTS/concurrency::target_block::sync_send
- AGENTS/concurrency::target_block::unlink_source
- AGENTS/concurrency::target_block::unlink_sources
- AGENTS/concurrency::target_block::wait_for_async_sends
dev_langs:
- C++
helpviewer_keywords:
- target_block class
ms.assetid: 3ce181b4-b94a-4894-bf7b-64fc09821f9f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 754bc6add99974ff204c977e47f35486cc830d95
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33693982"
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
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`source_iterator`|Тип итератора для `source_link_manager` для этого `target_block` объекта.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[target_block](#ctor)|Создает объект `target_block`.|  
|[~ target_block деструктор](#dtor)|Уничтожает `target_block` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[распространение](#propagate)|Асинхронно передает сообщение из исходного блока данному целевому блоку.|  
|[send](#send)|Для этого целевого блока синхронно передает сообщение из исходного блока.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[async_send](#async_send)|Асинхронно отправляет сообщение для обработки.|  
|[decline_incoming_messages](#decline_incoming_messages)|Указывает блоку, что новые сообщения должны быть отклонены.|  
|[enable_batched_processing](#enable_batched_processing)|Активирует пакетную обработку для этого блока.|  
|[initialize_target](#initialize_target)|Инициализирует базовый объект. В частности `message_processor` необходимо инициализировать объект.|  
|[link_source](#link_source)|Связывает указанный исходный блок этого `target_block` объекта.|  
|[process_input_messages](#process_input_messages)|Обрабатывает сообщения, полученные как входные данные.|  
|[process_message](#process_message)|При переопределении в производном классе обрабатывает сообщение, которое ранее было принято данным объектом `target_block`.|  
|[propagate_message](#propagate_message)|При переопределении в производном классе этот метод асинхронно передает сообщение от `ISource` блока к этому `target_block` объекта. Он вызывается по `propagate` метод при вызове исходного блока.|  
|[register_filter](#register_filter)|Регистрирует метод фильтра, который будет вызываться при каждом получении сообщения.|  
|[remove_sources](#remove_sources)|Удаляет связь все источники после ожидания в течение ожидающих операций асинхронной отправки для завершения.|  
|[send_message](#send_message)|При переопределении в производном классе этот метод синхронно передает сообщение от `ISource` блока к этому `target_block` объекта. Он вызывается по `send` метод при вызове исходного блока.|  
|[sync_send](#sync_send)|Синхронно отправляет сообщение для обработки.|  
|[unlink_source](#unlink_source)|Удаляет связь указанного блока источника из этого `target_block` объекта.|  
|[unlink_sources](#unlink_sources)|Удаляет связь всех исходных блоков из этого `target_block` объекта. (Переопределяет [ITarget::unlink_sources](itarget-class.md#unlink_sources).)|  
|[wait_for_async_sends](#wait_for_async_sends)|Ожидает завершения всех асинхронных операций распространения.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [ITarget](itarget-class.md)  
  
 `target_block`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="async_send"></a> async_send 

 Асинхронно отправляет сообщение для обработки.  
  
```
void async_send(_Inout_opt_ message<_Source_type>* _PMessage);
```  
  
### <a name="parameters"></a>Параметры  
 `_PMessage`  
 Указатель на сообщение было отправлено.  
  
##  <a name="decline_incoming_messages"></a> decline_incoming_messages 

 Указывает блоку, что новые сообщения должны быть отклонены.  
  
```
void decline_incoming_messages();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается деструктором, чтобы убедиться, что новые сообщения отклоняются во время уничтожения.  
  
##  <a name="enable_batched_processing"></a> enable_batched_processing 

 Активирует пакетную обработку для этого блока.  
  
```
void enable_batched_processing();
```  
  
##  <a name="initialize_target"></a> initialize_target 

 Инициализирует базовый объект. В частности `message_processor` необходимо инициализировать объект.  
  
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
  
##  <a name="link_source"></a> link_source 

 Связывает указанный исходный блок этого `target_block` объекта.  
  
```
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Параметры  
 `_PSource`  
 Указатель на `ISource` блок, который должен быть связан.  
  
### <a name="remarks"></a>Примечания  
 Эта функция не должен вызываться непосредственно на `target_block` объекта. Блоки должны быть соединены друг с другом с помощью `link_target` метод `ISource` блоков, который будет вызывать `link_source` метод в соответствующий целевой объект.  
  
##  <a name="process_input_messages"></a> process_input_messages 

 Обрабатывает сообщения, полученные как входные данные.  
  
```
virtual void process_input_messages(_Inout_ message<_Source_type>* _PMessage);
```  
  
### <a name="parameters"></a>Параметры  
 `_PMessage`  
  
##  <a name="process_message"></a> process_message 

 При переопределении в производном классе обрабатывает сообщение, которое ранее было принято данным объектом `target_block`.  
  
```
virtual void process_message(message<_Source_type> *);
```  
  
##  <a name="propagate"></a> распространение 

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
 Объект [message_status](concurrency-namespace-enums.md) , указывающее, что целевой объект решил сделать с сообщением.  
  
### <a name="remarks"></a>Примечания  
 Метод создает [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение, если параметр `_PMessage` или `_PSource` параметр `NULL`.  
  
##  <a name="propagate_message"></a> propagate_message 

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
 Объект [message_status](concurrency-namespace-enums.md) , указывающее, что целевой объект решил сделать с сообщением.  
  
##  <a name="register_filter"></a> register_filter 

 Регистрирует метод фильтра, который будет вызываться при каждом получении сообщения.  
  
```
void register_filter(filter_method const& _Filter);
```  
  
### <a name="parameters"></a>Параметры  
 `_Filter`  
 Метод фильтра.  
  
##  <a name="remove_sources"></a> remove_sources 

 Удаляет связь все источники после ожидания в течение ожидающих операций асинхронной отправки для завершения.  
  
```
void remove_sources();
```  
  
### <a name="remarks"></a>Примечания  
 Все целевые блоки должны вызывать данную процедуру для удаления источников в их деструкторе.  
  
##  <a name="send"></a> Отправить 

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
 Объект [message_status](concurrency-namespace-enums.md) , указывающее, что целевой объект решил сделать с сообщением.  
  
### <a name="remarks"></a>Примечания  
 Метод создает [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение, если параметр `_PMessage` или `_PSource` параметр `NULL`.  
  
 С помощью `send` метод вне инициации сообщения и передавать сообщения в сети является опасной операцией и может привести к взаимоблокировке.  
  
 Если `send` возвращает сообщение либо уже было принято и передачи в блок целевой или было отклонено целевым объектом.  
  
##  <a name="send_message"></a> send_message 

 При переопределении в производном классе этот метод синхронно передает сообщение от `ISource` блока к этому `target_block` объекта. Он вызывается по `send` метод при вызове исходного блока.  
  
```
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [message_status](concurrency-namespace-enums.md) , указывающее, что целевой объект решил сделать с сообщением.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот блок возвращает `declined` Если иное не переопределено в производном классе.  
  
##  <a name="sync_send"></a> sync_send 

 Синхронно отправляет сообщение для обработки.  
  
```
void sync_send(_Inout_opt_ message<_Source_type>* _PMessage);
```  
  
### <a name="parameters"></a>Параметры  
 `_PMessage`  
 Указатель на сообщение было отправлено.  
  
##  <a name="ctor"></a> target_block 

 Создает объект `target_block`.  
  
```
target_block();
```  
  
##  <a name="dtor"></a> ~ target_block 

 Уничтожает `target_block` объекта.  
  
```
virtual ~target_block();
```  
  
##  <a name="unlink_source"></a> unlink_source 

 Удаляет связь указанного блока источника из этого `target_block` объекта.  
  
```
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Параметры  
 `_PSource`  
 Указатель на `ISource` блок, который должен быть удалена.  
  
##  <a name="unlink_sources"></a> unlink_sources 

 Удаляет связь всех исходных блоков из этого `target_block` объекта.  
  
```
virtual void unlink_sources();
```  
  
##  <a name="wait_for_async_sends"></a> wait_for_async_sends 

 Ожидает завершения всех асинхронных операций распространения.  
  
```
void wait_for_async_sends();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод используется деструкторами блока сообщений, чтобы убедиться, что все асинхронные операции имели время для окончания перед удалением блока.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс ITarget](itarget-class.md)
