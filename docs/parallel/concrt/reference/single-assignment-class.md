---
title: "Класс single_assignment | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::single_assignment
dev_langs:
- C++
helpviewer_keywords:
- single_assignment class
ms.assetid: ccc34728-8de9-4e07-b83d-a36a58d9d2b9
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
ms.openlocfilehash: a2a500353b06219713c5d9f3e68f82b247c1604f
ms.lasthandoff: 02/24/2017

---
# <a name="singleassignment-class"></a>Класс single_assignment
Блок обмена сообщениями `single_assignment` — это упорядоченный блок `propagator_block` с несколькими источниками и несколькими целями, который может хранить один объект `message` с однократной записью.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>
class single_assignment : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип полезных данных сохраненных и распространенных буфером сообщения.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор single_assignment](#ctor)|Перегружен. Создает `single_assignment` блок обмена сообщениями.|  
|[~ single_assignment деструктор](#dtor)|Уничтожает `single_assignment` блоком сообщений.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[has_value метод](#has_value)|Проверяет, является ли это `single_assignment` блок сообщений еще инициализирован со значением.|  
|[значение метода](#value)|Возвращает ссылку на текущие полезную нагрузку сообщения, хранящуюся в `single_assignment` блоком сообщений.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[accept_message метод](#accept_message)|Принимает сообщение, предложенное это `single_assignment` блок сообщений, возвращая копию сообщения вызывающему объекту.|  
|[consume_message метод](#consume_message)|Потребляет сообщение, ранее предложенное `single_assignment` и зарезервированное целевым объектом, возвращая копию сообщения вызывающему объекту.|  
|[link_target_notification метод](#link_target_notification)|Обратный вызов, который уведомляет, что новая цель связана к этому `single_assignment` блок обмена сообщениями.|  
|[propagate_message метод](#propagate_message)|Асинхронно передает сообщение из `ISource` блока к этому `single_assignment` блок обмена сообщениями. Он вызывается по `propagate` метод при вызове исходного блока.|  
|[propagate_to_any_targets метод](#propagate_to_any_targets)|Окружение `message``_PMessage` в этом `single_assignment` блок обмена сообщениями и предоставляет его ко всем связанным целевым объектам.|  
|[release_message метод](#release_message)|Освобождает предыдущее резервирование сообщения. (Переопределяет [source_block::release_message](source-block-class.md#release_message).)|  
|[reserve_message метод](#reserve_message)|Резервирует сообщение, которое было предложено это `single_assignment` блок обмена сообщениями. (Переопределяет [source_block::reserve_message](source-block-class.md#reserve_message).)|  
|[resume_propagation метод](#resume_propagation)|Возобновляет распространение после выпуска резервирования. (Переопределяет [source_block::resume_propagation](source-block-class.md#resume_propagation).)|  
|[send_message метод](#send_message)|Синхронно передает сообщение от `ISource` блока к этому `single_assignment` блок обмена сообщениями. Он вызывается по `send` метод при вызове исходного блока.|  
  
## <a name="remarks"></a>Примечания  
 A `single_assignment` блок сообщений распространяет копии его сообщения для каждой цели.  
  
 Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [ISource](isource-class.md)  
  
 [ITarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 [propagator_block](propagator-block-class.md)  
  
 `single_assignment`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-nameacceptmessagea-acceptmessage"></a><a name="accept_message"></a>accept_message 

 Принимает сообщение, предложенное это `single_assignment` блок сообщений, возвращая копию сообщения вызывающему объекту.  
  
```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из предложенных `message` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `message` объект, вызывающий теперь принадлежит.  
  
### <a name="remarks"></a>Примечания  
 `single_assignment` Обмена сообщениями блок возвращает копии сообщения его целевым объектам, чем Передача владения текущего удержания сообщения.  
  
##  <a name="a-nameconsumemessagea-consumemessage"></a><a name="consume_message"></a>consume_message 

 Потребляет сообщение, ранее предложенное `single_assignment` и зарезервированное целевым объектом, возвращая копию сообщения вызывающему объекту.  
  
```
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из `message` объекта использованное.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `message` объект, вызывающий теперь принадлежит.  
  
### <a name="remarks"></a>Примечания  
 Аналогично `accept`, но всегда предшествует вызов `reserve`.  
  
##  <a name="a-namehasvaluea-hasvalue"></a><a name="has_value"></a>has_value 

 Проверяет, является ли это `single_assignment` блок сообщений еще инициализирован со значением.  
  
```
bool has_value() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если блок получил значение, `false` в противном случае.  
  
##  <a name="a-namelinktargetnotificationa-linktargetnotification"></a><a name="link_target_notification"></a>link_target_notification 

 Обратный вызов, который уведомляет, что новая цель связана к этому `single_assignment` блок обмена сообщениями.  
  
```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на только что привязанный целевой объект.  
  
##  <a name="a-namepropagatemessagea-propagatemessage"></a><a name="propagate_message"></a>propagate_message 

 Асинхронно передает сообщение из `ISource` блока к этому `single_assignment` блок обмена сообщениями. Он вызывается по `propagate` метод при вызове исходного блока.  
  
```
virtual message_status propagate_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```  
  
### <a name="parameters"></a>Параметры  
 `_PMessage`  
 Указатель на объект `message`.  
  
 `_PSource`  
 Указатель на исходный блок, предлагающий сообщение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [message_status](concurrency-namespace-enums.md) указывает на то, что целевой объект решил сделать с сообщением.  
  
##  <a name="a-namepropagatetoanytargetsa-propagatetoanytargets"></a><a name="propagate_to_any_targets"></a>propagate_to_any_targets 

 Окружение `message``_PMessage` в этом `single_assignment` блок обмена сообщениями и предоставляет его ко всем связанным целевым объектам.  
  
```
virtual void propagate_to_any_targets(_Inout_opt_ message<T>* _PMessage);
```  
  
### <a name="parameters"></a>Параметры  
 `_PMessage`  
 Указатель на `message` , `single_assignment` блок сообщений стал владельцем.  
  
##  <a name="a-namereleasemessagea-releasemessage"></a><a name="release_message"></a>release_message 

 Освобождает предыдущее резервирование сообщения.  
  
```
virtual void release_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из `message` объект освобожден.  
  
##  <a name="a-namereservemessagea-reservemessage"></a><a name="reserve_message"></a>reserve_message 

 Резервирует сообщение, которое было предложено это `single_assignment` блок обмена сообщениями.  
  
```
virtual bool reserve_message(runtime_object_identity _MsgId);
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

 Синхронно передает сообщение от `ISource` блока к этому `single_assignment` блок обмена сообщениями. Он вызывается по `send` метод при вызове исходного блока.  
  
```
virtual message_status send_message(
    _Inout_ message<T>* _PMessage,
    _Inout_ ISource<T>* _PSource);
```  
  
### <a name="parameters"></a>Параметры  
 `_PMessage`  
 Указатель на объект `message`.  
  
 `_PSource`  
 Указатель на исходный блок, предлагающий сообщение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект [message_status](concurrency-namespace-enums.md) указывает на то, что целевой объект решил сделать с сообщением.  
  
##  <a name="a-namectora-singleassignment"></a><a name="ctor"></a>single_assignment 

 Создает `single_assignment` блок обмена сообщениями.  
  
```
single_assignment();

single_assignment(
    filter_method const& _Filter);

single_assignment(
    Scheduler& _PScheduler);

single_assignment(
    Scheduler& _PScheduler,
    filter_method const& _Filter);

single_assignment(
    ScheduleGroup& _PScheduleGroup);

single_assignment(
    ScheduleGroup& _PScheduleGroup,
    filter_method const& _Filter);
```  
  
### <a name="parameters"></a>Параметры  
 `_Filter`  
 Функции фильтра, который определяет, следует ли принять предложенное сообщения.  
  
 `_PScheduler`  
 `Scheduler` Объекта, в течение которого задача распространения `single_assignment` запланирована блок обмена сообщениями.  
  
 `_PScheduleGroup`  
 `ScheduleGroup` Объекта, в течение которого задача распространения `single_assignment` запланирована блок обмена сообщениями. Используемый объект `Scheduler` подразумевается группой расписаний.  
  
### <a name="remarks"></a>Примечания  
 Среда выполнения использует планировщик по умолчанию, если вы не указали параметры `_PScheduler` или `_PScheduleGroup` .  
  
 Тип `filter_method` является функтор подписью `bool (T const &)` которого вызывается этим `single_assignment` блок сообщений, чтобы определить ли он должен принять предложенное сообщение.  
  
##  <a name="a-namedtora-singleassignment"></a><a name="dtor"></a>~ single_assignment 

 Уничтожает `single_assignment` блоком сообщений.  
  
```
~single_assignment();
```  
  
##  <a name="a-namevaluea-value"></a><a name="value"></a>значение 

 Возвращает ссылку на текущие полезную нагрузку сообщения, хранящуюся в `single_assignment` блоком сообщений.  
  
```
T const& value();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Полезные данные сохраненного сообщения.  
  
### <a name="remarks"></a>Примечания  
 Этот метод будет ожидать появления сообщения, если нет сохраненных в `single_assignment` блоком сообщений.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс overwrite_buffer](overwrite-buffer-class.md)   
 [Класс unbounded_buffer](unbounded-buffer-class.md)


