---
title: Класс single_assignment | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- single_assignment
- AGENTS/concurrency::single_assignment
- AGENTS/concurrency::single_assignment::single_assignment
- AGENTS/concurrency::single_assignment::has_value
- AGENTS/concurrency::single_assignment::value
- AGENTS/concurrency::single_assignment::accept_message
- AGENTS/concurrency::single_assignment::consume_message
- AGENTS/concurrency::single_assignment::link_target_notification
- AGENTS/concurrency::single_assignment::propagate_message
- AGENTS/concurrency::single_assignment::propagate_to_any_targets
- AGENTS/concurrency::single_assignment::release_message
- AGENTS/concurrency::single_assignment::reserve_message
- AGENTS/concurrency::single_assignment::resume_propagation
- AGENTS/concurrency::single_assignment::send_message
dev_langs:
- C++
helpviewer_keywords:
- single_assignment class
ms.assetid: ccc34728-8de9-4e07-b83d-a36a58d9d2b9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4bacbdaa4af141101863b4d6d81d114d43aced9f
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
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
 Тип полезных данных сообщения сохраненных и распространенных буфером.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[single_assignment](#ctor)|Перегружен. Создает `single_assignment` блока обмена сообщениями.|  
|[~ single_assignment деструктор](#dtor)|Уничтожает `single_assignment` блока обмена сообщениями.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[has_value](#has_value)|Проверяет, является ли это `single_assignment` блока обмена сообщениями еще была инициализирована со значением.|  
|[value](#value)|Возвращает ссылку на текущие полезную нагрузку сообщения, хранящуюся в `single_assignment` блока обмена сообщениями.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[accept_message](#accept_message)|Принимает сообщение, которое было предложено это `single_assignment` блока обмена сообщениями, возвращая копию сообщения вызывающему объекту.|  
|[consume_message](#consume_message)|Получает сообщение, ранее предложенное `single_assignment` и зарезервированные целевым объектом, возвращая копию сообщения вызывающему объекту.|  
|[link_target_notification](#link_target_notification)|Обратный вызов, уведомляющее о том, что новый целевой объект был связан это `single_assignment` блока обмена сообщениями.|  
|[propagate_message](#propagate_message)|Асинхронно передает сообщение от `ISource` блока к этому `single_assignment` блока обмена сообщениями. Он вызывается по `propagate` метод при вызове исходного блока.|  
|[propagate_to_any_targets](#propagate_to_any_targets)|Окружение `message _PMessage` в этом `single_assignment` блок обмена сообщениями и предоставляет его ко всем связанным целевым объектам.|  
|[release_message](#release_message)|Освобождает предыдущее резервирование сообщения. (Переопределяет [source_block::release_message](source-block-class.md#release_message).)|  
|[reserve_message](#reserve_message)|Резервирует сообщение, которое было предложено это `single_assignment` блока обмена сообщениями. (Переопределяет [source_block::reserve_message](source-block-class.md#reserve_message).)|  
|[resume_propagation](#resume_propagation)|Возобновляет распространение после выпуска резервирования. (Переопределяет [source_block::resume_propagation](source-block-class.md#resume_propagation).)|  
|[send_message](#send_message)|Синхронно передает сообщение от `ISource` блока к этому `single_assignment` блока обмена сообщениями. Он вызывается по `send` метод при вызове исходного блока.|  
  
## <a name="remarks"></a>Примечания  
 Объект `single_assignment` блока обмена сообщениями распространяет копии его сообщения для каждой цели.  
  
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
  
##  <a name="accept_message"></a> accept_message 

 Принимает сообщение, которое было предложено это `single_assignment` блока обмена сообщениями, возвращая копию сообщения вызывающему объекту.  
  
```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из предложенных `message` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `message` объект, вызывающий теперь принадлежит.  
  
### <a name="remarks"></a>Примечания  
 `single_assignment` Обмена сообщениями возвращает блок копии сообщения целевым, а не передавать владение текущего удержания сообщения.  
  
##  <a name="consume_message"></a> consume_message 

 Получает сообщение, ранее предложенное `single_assignment` и зарезервированные целевым объектом, возвращая копию сообщения вызывающему объекту.  
  
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

 Проверяет, является ли это `single_assignment` блока обмена сообщениями еще была инициализирована со значением.  
  
```
bool has_value() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если блок получил значение, `false` в противном случае.  
  
##  <a name="link_target_notification"></a> link_target_notification 

 Обратный вызов, уведомляющее о том, что новый целевой объект был связан это `single_assignment` блока обмена сообщениями.  
  
```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на только что привязанный целевой объект.  
  
##  <a name="propagate_message"></a> propagate_message 

 Асинхронно передает сообщение от `ISource` блока к этому `single_assignment` блока обмена сообщениями. Он вызывается по `propagate` метод при вызове исходного блока.  
  
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

 Окружение `message` `_PMessage` в этом `single_assignment` блок обмена сообщениями и предоставляет его ко всем связанным целевым объектам.  
  
```
virtual void propagate_to_any_targets(_Inout_opt_ message<T>* _PMessage);
```  
  
### <a name="parameters"></a>Параметры  
 `_PMessage`  
 Указатель на `message` этим `single_assignment` блока обмена сообщениями станет владельцем данных.  
  
##  <a name="release_message"></a> release_message 

 Освобождает предыдущее резервирование сообщения.  
  
```
virtual void release_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из `message` объекта освобождение.  
  
##  <a name="reserve_message"></a> reserve_message 

 Резервирует сообщение, которое было предложено это `single_assignment` блока обмена сообщениями.  
  
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
  
##  <a name="send_message"></a> send_message 

 Синхронно передает сообщение от `ISource` блока к этому `single_assignment` блока обмена сообщениями. Он вызывается по `send` метод при вызове исходного блока.  
  
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
  
##  <a name="ctor"></a> single_assignment 

 Создает `single_assignment` блока обмена сообщениями.  
  
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
 Функции фильтров, который определяет, следует ли принять предложенное сообщения.  
  
 `_PScheduler`  
 `Scheduler` Объекта, в течение которого задача распространения для `single_assignment` запланирована блока обмена сообщениями.  
  
 `_PScheduleGroup`  
 `ScheduleGroup` Объекта, в течение которого задача распространения для `single_assignment` запланирована блока обмена сообщениями. Используемый объект `Scheduler` подразумевается группой расписаний.  
  
### <a name="remarks"></a>Примечания  
 Среда выполнения использует планировщик по умолчанию, если вы не указали параметры `_PScheduler` или `_PScheduleGroup` .  
  
 Тип `filter_method` является функтор с сигнатурой `bool (T const &)` которого вызывается этим `single_assignment` блока обмена сообщениями, чтобы определить ли он должен принять предложенное сообщение.  
  
##  <a name="dtor"></a> ~ single_assignment 

 Уничтожает `single_assignment` блока обмена сообщениями.  
  
```
~single_assignment();
```  
  
##  <a name="value"></a> Значение 

 Возвращает ссылку на текущие полезную нагрузку сообщения, хранящуюся в `single_assignment` блока обмена сообщениями.  
  
```
T const& value();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Полезные данные сохраненного сообщения.  
  
### <a name="remarks"></a>Примечания  
 Этот метод будет ожидать появления сообщения, если нет сохраненных в `single_assignment` блока обмена сообщениями.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс overwrite_buffer](overwrite-buffer-class.md)   
 [Класс unbounded_buffer](unbounded-buffer-class.md)

