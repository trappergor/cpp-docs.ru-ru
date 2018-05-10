---
title: Класс overwrite_buffer | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- overwrite_buffer
- AGENTS/concurrency::overwrite_buffer
- AGENTS/concurrency::overwrite_buffer::overwrite_buffer
- AGENTS/concurrency::overwrite_buffer::has_value
- AGENTS/concurrency::overwrite_buffer::value
- AGENTS/concurrency::overwrite_buffer::accept_message
- AGENTS/concurrency::overwrite_buffer::consume_message
- AGENTS/concurrency::overwrite_buffer::link_target_notification
- AGENTS/concurrency::overwrite_buffer::propagate_message
- AGENTS/concurrency::overwrite_buffer::propagate_to_any_targets
- AGENTS/concurrency::overwrite_buffer::release_message
- AGENTS/concurrency::overwrite_buffer::reserve_message
- AGENTS/concurrency::overwrite_buffer::resume_propagation
- AGENTS/concurrency::overwrite_buffer::send_message
- AGENTS/concurrency::overwrite_buffer::supports_anonymous_source
dev_langs:
- C++
helpviewer_keywords:
- overwrite_buffer class
ms.assetid: 5cc428fe-3697-419c-9fb2-78f6181c9293
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: dccde651898bf5ff0986dc2e577a1d2ee5765e3f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="overwritebuffer-class"></a>Класс overwrite_buffer
Блок обмена сообщениями `overwrite_buffer` — это упорядоченный блок `propagator_block` с несколькими источниками и несколькими целями, который может хранить одно сообщение в один момент времени. Новые сообщения перезаписывают предыдущие.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>
class overwrite_buffer : public propagator_block<multi_link_registry<ITarget<T>>, multi_link_registry<ISource<T>>>;
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип полезных данных сохраненных и распространенных буфером сообщений.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[overwrite_buffer](#ctor)|Перегружен. Создает `overwrite_buffer` блока обмена сообщениями.|  
|[~ overwrite_buffer деструктор](#dtor)|Уничтожает `overwrite_buffer` блока обмена сообщениями.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[has_value](#has_value)|Проверяет, является ли это `overwrite_buffer` блока обмена сообщениями еще имеет значение.|  
|[value](#value)|Возвращает ссылку на текущие полезную нагрузку сообщения, хранящуюся в `overwrite_buffer` блока обмена сообщениями.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[accept_message](#accept_message)|Принимает сообщение, которое было предложено это `overwrite_buffer` блока обмена сообщениями, возвращая копию сообщения вызывающему объекту.|  
|[consume_message](#consume_message)|Получает сообщение, ранее предложенное `overwrite_buffer` блок обмена сообщениями и зарезервированное целевым объектом, возвращая копию сообщения вызывающему объекту.|  
|[link_target_notification](#link_target_notification)|Обратный вызов, уведомляющее о том, что новый целевой объект был связан это `overwrite_buffer` блока обмена сообщениями.|  
|[propagate_message](#propagate_message)|Асинхронно передает сообщение от `ISource` блока к этому `overwrite_buffer` блока обмена сообщениями. Он вызывается по `propagate` метод при вызове исходного блока.|  
|[propagate_to_any_targets](#propagate_to_any_targets)|Окружение `message _PMessage` в этом `overwrite_buffer` блок обмена сообщениями и предоставляет его ко всем связанным целевым объектам.|  
|[release_message](#release_message)|Освобождает предыдущее резервирование сообщения. (Переопределяет [source_block::release_message](source-block-class.md#release_message).)|  
|[reserve_message](#reserve_message)|Резервирует сообщение, которое было предложено это `overwrite_buffer` блока обмена сообщениями. (Переопределяет [source_block::reserve_message](source-block-class.md#reserve_message).)|  
|[resume_propagation](#resume_propagation)|Возобновляет распространение после выпуска резервирования. (Переопределяет [source_block::resume_propagation](source-block-class.md#resume_propagation).)|  
|[send_message](#send_message)|Синхронно передает сообщение от `ISource` блока к этому `overwrite_buffer` блока обмена сообщениями. Он вызывается по `send` метод при вызове исходного блока.|  
|[supports_anonymous_source](#supports_anonymous_source)|Переопределяет метод `supports_anonymous_source`, чтобы указать, что данный блок может принимать сообщения, предоставляемые ему несвязанным источником. (Переопределяет [ITarget::supports_anonymous_source](itarget-class.md#supports_anonymous_source).)|  
  
## <a name="remarks"></a>Примечания  
 `overwrite_buffer` Блока обмена сообщениями распространяет копии своего сохраненного сообщения для каждого из его целевых объектов.  
  
 Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [ISource](isource-class.md)  
  
 [ITarget](itarget-class.md)  
  
 [source_block](source-block-class.md)  
  
 [propagator_block](propagator-block-class.md)  
  
 `overwrite_buffer`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="accept_message"></a> accept_message 

 Принимает сообщение, которое было предложено это `overwrite_buffer` блока обмена сообщениями, возвращая копию сообщения вызывающему объекту.  
  
```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из предложенных `message` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `message` объект, вызывающий теперь принадлежит.  
  
### <a name="remarks"></a>Примечания  
 `overwrite_buffer` Обмена сообщениями возвращает блок копии сообщения целевым, а не передавать владение текущего удержания сообщения.  
  
##  <a name="consume_message"></a> consume_message 

 Получает сообщение, ранее предложенное `overwrite_buffer` блок обмена сообщениями и зарезервированное целевым объектом, возвращая копию сообщения вызывающему объекту.  
  
```
virtual message<T>* consume_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из `message` объект используется.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `message` объект, вызывающий теперь принадлежит.  
  
### <a name="remarks"></a>Примечания  
 Аналогично `accept`, но всегда предшествует вызов `reserve`.  
  
##  <a name="has_value"></a> has_value 

 Проверяет, является ли это `overwrite_buffer` блока обмена сообщениями еще имеет значение.  
  
```
bool has_value() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если блок получил значение, `false` в противном случае.  
  
##  <a name="link_target_notification"></a> link_target_notification 

 Обратный вызов, уведомляющее о том, что новый целевой объект был связан это `overwrite_buffer` блока обмена сообщениями.  
  
```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на только что привязанный целевой объект.  
  
##  <a name="dtor"></a> ~ overwrite_buffer 

 Уничтожает `overwrite_buffer` блока обмена сообщениями.  
  
```
~overwrite_buffer();
```  
  
##  <a name="ctor"></a> overwrite_buffer 

 Создает `overwrite_buffer` блока обмена сообщениями.  
  
```
overwrite_buffer();

overwrite_buffer(
    filter_method const& _Filter);

overwrite_buffer(
    Scheduler& _PScheduler);

overwrite_buffer(
    Scheduler& _PScheduler,
    filter_method const& _Filter);

overwrite_buffer(
    ScheduleGroup& _PScheduleGroup);

overwrite_buffer(
    ScheduleGroup& _PScheduleGroup,
    filter_method const& _Filter);
```  
  
### <a name="parameters"></a>Параметры  
 `_Filter`  
 Функции фильтров, который определяет, следует ли принять предложенное сообщения.  
  
 `_PScheduler`  
 `Scheduler` Объекта, в течение которого задача распространения для `overwrite_buffer` запланирована блока обмена сообщениями.  
  
 `_PScheduleGroup`  
 `ScheduleGroup` Объекта, в течение которого задача распространения для `overwrite_buffer` запланирована блока обмена сообщениями. Используемый объект `Scheduler` подразумевается группой расписаний.  
  
### <a name="remarks"></a>Примечания  
 Среда выполнения использует планировщик по умолчанию, если вы не указали параметры `_PScheduler` или `_PScheduleGroup` .  
  
 Тип `filter_method` является функтор с сигнатурой `bool (T const &)` которого вызывается этим `overwrite_buffer` блока обмена сообщениями, чтобы определить ли он должен принять предложенное сообщение.  
  
##  <a name="propagate_message"></a> propagate_message 

 Асинхронно передает сообщение от `ISource` блока к этому `overwrite_buffer` блока обмена сообщениями. Он вызывается по `propagate` метод при вызове исходного блока.  
  
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
 Объект [message_status](concurrency-namespace-enums.md) , указывающее, что целевой объект решил сделать с сообщением.  
  
##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets 

 Окружение `message _PMessage` в этом `overwrite_buffer` блок обмена сообщениями и предоставляет его ко всем связанным целевым объектам.  
  
```
virtual void propagate_to_any_targets(_Inout_ message<T>* _PMessage);
```  
  
### <a name="parameters"></a>Параметры  
 `_PMessage`  
 Указатель на `message` объекта этим `overwrite_buffer` стал владельцем.  
  
### <a name="remarks"></a>Примечания  
 Этот метод перезаписывает текущего сообщения в `overwrite_buffer` принятое сообщение `_PMessage`.  
  
##  <a name="send_message"></a> send_message 

 Синхронно передает сообщение от `ISource` блока к этому `overwrite_buffer` блока обмена сообщениями. Он вызывается по `send` метод при вызове исходного блока.  
  
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
 Объект [message_status](concurrency-namespace-enums.md) , указывающее, что целевой объект решил сделать с сообщением.  
  
##  <a name="supports_anonymous_source"></a> supports_anonymous_source 

 Переопределяет метод `supports_anonymous_source`, чтобы указать, что данный блок может принимать сообщения, предоставляемые ему несвязанным источником.  
  
```
virtual bool supports_anonymous_source();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение `true`, поскольку блок не откладывает предоставляемые сообщения.  
  
##  <a name="release_message"></a> release_message 

 Освобождает предыдущее резервирование сообщения.  
  
```
virtual void release_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из `message` объекта освобождение.  
  
##  <a name="reserve_message"></a> reserve_message 

 Резервирует сообщение, которое было предложено это `overwrite_buffer` блока обмена сообщениями.  
  
```
virtual bool reserve_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из `message` объекта резервируются.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если сообщение было успешно зарезервированы, `false` в противном случае.  
  
### <a name="remarks"></a>Примечания  
 После `reserve` вызывается, если он возвращает `true`, либо `consume` или `release` необходимо вызвать, чтобы принять или высвободить владение сообщением.  
  
##  <a name="resume_propagation"></a> resume_propagation 

 Возобновляет распространение после выпуска резервирования.  
  
```
virtual void resume_propagation();
```  
  
##  <a name="value"></a> Значение 

 Возвращает ссылку на текущие полезную нагрузку сообщения, хранящуюся в `overwrite_buffer` блока обмена сообщениями.  
  
```
T value();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Полезные данные в данный момент сохраненного сообщения.  
  
### <a name="remarks"></a>Примечания  
 Значение, хранящееся в `overwrite_buffer` удалось изменить сразу после возврата этого метода. Этот метод будет ожидать появления сообщения, если нет сохраненных в `overwrite_buffer`.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс unbounded_buffer](unbounded-buffer-class.md)   
 [Класс single_assignment](single-assignment-class.md)
