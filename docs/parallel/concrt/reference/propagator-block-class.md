---
title: "Класс propagator_block | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- propagator_block
- AGENTS/concurrency::propagator_block
- AGENTS/concurrency::propagator_block::propagator_block
- AGENTS/concurrency::propagator_block::propagate
- AGENTS/concurrency::propagator_block::send
- AGENTS/concurrency::propagator_block::decline_incoming_messages
- AGENTS/concurrency::propagator_block::initialize_source_and_target
- AGENTS/concurrency::propagator_block::link_source
- AGENTS/concurrency::propagator_block::process_input_messages
- AGENTS/concurrency::propagator_block::propagate_message
- AGENTS/concurrency::propagator_block::register_filter
- AGENTS/concurrency::propagator_block::remove_network_links
- AGENTS/concurrency::propagator_block::send_message
- AGENTS/concurrency::propagator_block::unlink_source
- AGENTS/concurrency::propagator_block::unlink_sources
dev_langs: C++
helpviewer_keywords: propagator_block class
ms.assetid: 86aa75fd-eda5-42aa-aadf-25c0c1c9742d
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ff31849020c9daed7999ae1569e8c12249a4b834
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="propagatorblock-class"></a>Класс propagator_block
Класс `propagator_block` — это абстрактный базовый класс для блоков сообщений, которые являются одновременно блоками источников и целевыми блоками. Он объединяет функциональные возможности обоих классов, `source_block` и `target_block`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class _TargetLinkRegistry, class _SourceLinkRegistry, class _MessageProcessorType = ordered_message_processor<typename _TargetLinkRegistry::type::type>>
class propagator_block : public source_block<_TargetLinkRegistry,
    _MessageProcessorType>,
 public ITarget<typename _SourceLinkRegistry::type::source_type>;
```  
  
#### <a name="parameters"></a>Параметры  
 `_TargetLinkRegistry`  
 Реестр ссылок для использования для хранения целевых ссылок.  
  
 `_SourceLinkRegistry`  
 Реестр ссылок для использования для хранения исходных ссылок.  
  
 `_MessageProcessorType`  
 Тип процессора для обработки сообщений.  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|`source_iterator`|Тип итератора для `source_link_manager` для этого `propagator_block`.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[propagator_block](#ctor)|Создает объект `propagator_block`.|  
|[~ propagator_block деструктор](#dtor)|Уничтожает объект `propagator_block`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[распространение](#propagate)|Асинхронно передает сообщение из исходного блока данному целевому блоку.|  
|[send](#send)|Синхронно инициирует сообщения в этот блок. Вызывается методом `ISource` блока. По завершении этой функции сообщение уже будет распространено в блок.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[decline_incoming_messages](#decline_incoming_messages)|Указывает блоку, что новые сообщения должны быть отклонены.|  
|[initialize_source_and_target](#initialize_source_and_target)|Инициализирует базовый объект. В частности `message_processor` необходимо инициализировать объект.|  
|[link_source](#link_source)|Связывает указанный исходный блок этого `propagator_block` объекта.|  
|[process_input_messages](#process_input_messages)|Обработка входных сообщений. Это полезно только для блоков распространения, производных от source_block (переопределяет [source_block::process_input_messages](source-block-class.md#process_input_messages).)|  
|[propagate_message](#propagate_message)|При переопределении в производном классе этот метод асинхронно передает сообщение от `ISource` блока к этому `propagator_block` объекта. Он вызывается по `propagate` метод при вызове исходного блока.|  
|[register_filter](#register_filter)|Регистрирует метод фильтра, который будет вызываться для каждого полученного сообщения.|  
|[remove_network_links](#remove_network_links)|Удаляет все исходной и целевой сети ссылки из этого `propagator_block` объекта.|  
|[send_message](#send_message)|При переопределении в производном классе этот метод синхронно передает сообщение от `ISource` блока к этому `propagator_block` объекта. Он вызывается по `send` метод при вызове исходного блока.|  
|[unlink_source](#unlink_source)|Удаляет связь указанного блока источника из этого `propagator_block` объекта.|  
|[unlink_sources](#unlink_sources)|Удаляет связь всех исходных блоков из этого `propagator_block` объекта. (Переопределяет [ITarget::unlink_sources](itarget-class.md#unlink_sources).)|  
  
## <a name="remarks"></a>Примечания  
 Чтобы избежать множественное наследование `propagator_block` класс наследует от `source_block` класса и `ITarget` абстрактного класса. Большинство функций в `target_block` класса реплицируется здесь.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [ISource](isource-class.md)  
  
 [ITarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 `propagator_block`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="decline_incoming_messages"></a>decline_incoming_messages 

 Указывает блоку, что новые сообщения должны быть отклонены.  
  
```
void decline_incoming_messages();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается деструктором, чтобы убедиться, что новые сообщения отклоняются во время уничтожения.  
  
##  <a name="initialize_source_and_target"></a>initialize_source_and_target 

 Инициализирует базовый объект. В частности `message_processor` необходимо инициализировать объект.  
  
```
void initialize_source_and_target(
    _Inout_opt_ Scheduler* _PScheduler = NULL,
    _Inout_opt_ ScheduleGroup* _PScheduleGroup = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `_PScheduler`  
 Планировщик, будет использоваться для планирования задач.  
  
 `_PScheduleGroup`  
 Группа расписаний, которая будет использоваться для планирования задач.  
  
##  <a name="link_source"></a>link_source 

 Связывает указанный исходный блок этого `propagator_block` объекта.  
  
```
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Параметры  
 `_PSource`  
 Указатель на `ISource` блок, который должен быть связан.  
  
##  <a name="process_input_messages"></a>process_input_messages 

 Обработка входных сообщений. Подходит только для блоков распространения, производных от source_block.  
  
```
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```  
  
### <a name="parameters"></a>Параметры  
 `_PMessage`  
  
##  <a name="propagate"></a>распространение 

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
 `propagate` Метод вызван на целевой блок связанного исходного блока. Ставит асинхронную задачу для обработки сообщения, если одно не уже находится в очереди или выполнения.  
  
 Метод создает [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение, если параметр `_PMessage` или `_PSource` параметр `NULL`.  
  
##  <a name="propagate_message"></a>propagate_message 

 При переопределении в производном классе этот метод асинхронно передает сообщение от `ISource` блока к этому `propagator_block` объекта. Он вызывается по `propagate` метод при вызове исходного блока.  
  
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
  
##  <a name="ctor"></a>propagator_block 

 Создает объект `propagator_block`.  
  
```
propagator_block();
```  
  
##  <a name="dtor"></a>~ propagator_block 

 Уничтожает объект `propagator_block`.  
  
```
virtual ~propagator_block();
```  
  
##  <a name="register_filter"></a>register_filter 

 Регистрирует метод фильтра, который будет вызываться для каждого полученного сообщения.  
  
```
void register_filter(filter_method const& _Filter);
```  
  
### <a name="parameters"></a>Параметры  
 `_Filter`  
 Метод фильтра.  
  
##  <a name="remove_network_links"></a>remove_network_links 

 Удаляет все исходной и целевой сети ссылки из этого `propagator_block` объекта.  
  
```
void remove_network_links();
```  
  
##  <a name="send"></a>Отправить 

 Синхронно инициирует сообщения в этот блок. Вызывается методом `ISource` блока. По завершении этой функции сообщение уже будет распространено в блок.  
  
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
 Этот метод создает исключение [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение, если параметр `_PMessage` или `_PSource` параметр `NULL`.  
  
##  <a name="send_message"></a>send_message 

 При переопределении в производном классе этот метод синхронно передает сообщение от `ISource` блока к этому `propagator_block` объекта. Он вызывается по `send` метод при вызове исходного блока.  
  
```
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [message_status](concurrency-namespace-enums.md) , указывающее, что целевой объект решил сделать с сообщением.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот блок возвращает `declined` Если иное не переопределено в производном классе.  
  
##  <a name="unlink_source"></a>unlink_source 

 Удаляет связь указанного блока источника из этого `propagator_block` объекта.  
  
```
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Параметры  
 `_PSource`  
 Указатель на `ISource` блок, который должен быть удалена.  
  
##  <a name="unlink_sources"></a>unlink_sources 

 Удаляет связь всех исходных блоков из этого `propagator_block` объекта.  
  
```
virtual void unlink_sources();
```  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс source_block](source-block-class.md)   
 [Класс ITarget](itarget-class.md)
