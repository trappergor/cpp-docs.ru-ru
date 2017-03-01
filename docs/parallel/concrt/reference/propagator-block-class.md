---
title: "Класс propagator_block | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::propagator_block
dev_langs:
- C++
helpviewer_keywords:
- propagator_block class
ms.assetid: 86aa75fd-eda5-42aa-aadf-25c0c1c9742d
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
ms.openlocfilehash: b53577fc187d699f50b4095518e9bc3562dcc7f3
ms.lasthandoff: 02/24/2017

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
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`source_iterator`|Тип итератора для `source_link_manager` для этого `propagator_block`.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор propagator_block](#ctor)|Создает объект `propagator_block`.|  
|[~ propagator_block деструктор](#dtor)|Уничтожает объект `propagator_block`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Propagate-метод](#propagate)|Асинхронно передает сообщение из исходного блока данному целевому блоку.|  
|[Send-метод](#send)|Синхронно запускает сообщения в этот блок. Вызывается методом `ISource` блок. По завершении этой функции сообщение уже будет распространено в блок.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[decline_incoming_messages метод](#decline_incoming_messages)|Указывает блоку, что новые сообщения должны быть отклонены.|  
|[initialize_source_and_target метод](#initialize_source_and_target)|Инициализирует базовый объект. В частности `message_processor` объект необходимо инициализировать.|  
|[link_source метод](#link_source)|Связывает указанный целевой блок это `propagator_block` объекта.|  
|[process_input_messages метод](#process_input_messages)|Обработка входных сообщений. Это полезно только для блоков распространения, производных от source_block (переопределяет [source_block::process_input_messages](source-block-class.md#process_input_messages).)|  
|[propagate_message метод](#propagate_message)|При переопределении в производном классе этот метод асинхронно передает сообщение от `ISource` блока к этому `propagator_block` объекта. Он вызывается по `propagate` метод при вызове исходного блока.|  
|[register_filter метод](#register_filter)|Регистрирует метод фильтра, который будет вызван на каждое полученное сообщение.|  
|[remove_network_links метод](#remove_network_links)|Удаляет все исходной и целевой сети ссылки из этого `propagator_block` объекта.|  
|[send_message метод](#send_message)|При переопределении в производном классе этот метод синхронно передает сообщение от `ISource` блока к этому `propagator_block` объекта. Он вызывается по `send` метод при вызове исходного блока.|  
|[unlink_source метод](#unlink_source)|Удаляет связь указанного блока источника из этого `propagator_block` объекта.|  
|[unlink_sources метод](#unlink_sources)|Удаляет связь всех исходных блоков от этого `propagator_block` объекта. (Переопределяет [ITarget::unlink_sources](itarget-class.md#unlink_sources).)|  
  
## <a name="remarks"></a>Примечания  
 Чтобы избежать множественное наследование, `propagator_block` класс наследует от `source_block` класса и `ITarget` абстрактного класса. Большинство функциональных возможностей в `target_block` класса реплицируется здесь.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [ISource](isource-class.md)  
  
 [ITarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 `propagator_block`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namedeclineincomingmessagesa-declineincomingmessages"></a><a name="decline_incoming_messages"></a>decline_incoming_messages 

 Указывает блоку, что новые сообщения должны быть отклонены.  
  
```
void decline_incoming_messages();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается деструктором, чтобы убедиться, что новые сообщения отклоняются во время уничтожения.  
  
##  <a name="a-nameinitializesourceandtargeta-initializesourceandtarget"></a><a name="initialize_source_and_target"></a>initialize_source_and_target 

 Инициализирует базовый объект. В частности `message_processor` объект необходимо инициализировать.  
  
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
  
##  <a name="a-namelinksourcea-linksource"></a><a name="link_source"></a>link_source 

 Связывает указанный целевой блок это `propagator_block` объекта.  
  
```
virtual void link_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Параметры  
 `_PSource`  
 Указатель на `ISource` блок, который должен быть связан.  
  
##  <a name="a-nameprocessinputmessagesa-processinputmessages"></a><a name="process_input_messages"></a>process_input_messages 

 Обработка входных сообщений. Подходит только для блоков распространения, производных от source_block.  
  
```
virtual void process_input_messages(_Inout_ message<_Target_type>* _PMessage);
```  
  
### <a name="parameters"></a>Параметры  
 `_PMessage`  
  
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
 `propagate` Метод вызывается на целевом блоке блоком связанного источника. Ставит асинхронную задачу для обработки сообщения, если один не уже находится в очереди или выполнения.  
  
 Метод создает [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение, если любой `_PMessage` или `_PSource` параметр `NULL`.  
  
##  <a name="a-namepropagatemessagea-propagatemessage"></a><a name="propagate_message"></a>propagate_message 

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
 Объект [message_status](concurrency-namespace-enums.md) указывает на то, что целевой объект решил сделать с сообщением.  
  
##  <a name="a-namectora-propagatorblock"></a><a name="ctor"></a>propagator_block 

 Создает объект `propagator_block`.  
  
```
propagator_block();
```  
  
##  <a name="a-namedtora-propagatorblock"></a><a name="dtor"></a>~ propagator_block 

 Уничтожает объект `propagator_block`.  
  
```
virtual ~propagator_block();
```  
  
##  <a name="a-nameregisterfiltera-registerfilter"></a><a name="register_filter"></a>register_filter 

 Регистрирует метод фильтра, который будет вызван на каждое полученное сообщение.  
  
```
void register_filter(filter_method const& _Filter);
```  
  
### <a name="parameters"></a>Параметры  
 `_Filter`  
 Метод фильтра.  
  
##  <a name="a-nameremovenetworklinksa-removenetworklinks"></a><a name="remove_network_links"></a>remove_network_links 

 Удаляет все исходной и целевой сети ссылки из этого `propagator_block` объекта.  
  
```
void remove_network_links();
```  
  
##  <a name="a-namesenda-send"></a><a name="send"></a>Отправить 

 Синхронно запускает сообщения в этот блок. Вызывается методом `ISource` блок. По завершении этой функции сообщение уже будет распространено в блок.  
  
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
 Этот метод создает исключение [invalid_argument](../../../standard-library/invalid-argument-class.md) исключение, если любой `_PMessage` или `_PSource` параметр `NULL`.  
  
##  <a name="a-namesendmessagea-sendmessage"></a><a name="send_message"></a>send_message 

 При переопределении в производном классе этот метод синхронно передает сообщение от `ISource` блока к этому `propagator_block` объекта. Он вызывается по `send` метод при вызове исходного блока.  
  
```
virtual message_status send_message(
    _Inout_ message<_Source_type> *,
    _Inout_ ISource<_Source_type> *);
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [message_status](concurrency-namespace-enums.md) указывает на то, что целевой объект решил сделать с сообщением.  
  
### <a name="remarks"></a>Примечания  
 По умолчанию этот блок возвращает `declined` Если не переопределено в производном классе.  
  
##  <a name="a-nameunlinksourcea-unlinksource"></a><a name="unlink_source"></a>unlink_source 

 Удаляет связь указанного блока источника из этого `propagator_block` объекта.  
  
```
virtual void unlink_source(_Inout_ ISource<_Source_type>* _PSource);
```  
  
### <a name="parameters"></a>Параметры  
 `_PSource`  
 Указатель на `ISource` блок, который должен быть удалена.  
  
##  <a name="a-nameunlinksourcesa-unlinksources"></a><a name="unlink_sources"></a>unlink_sources 

 Удаляет связь всех исходных блоков от этого `propagator_block` объекта.  
  
```
virtual void unlink_sources();
```  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс source_block](source-block-class.md)   
 [Класс ITarget](itarget-class.md)

