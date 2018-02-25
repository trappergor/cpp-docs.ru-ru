---
title: "Класс Timer | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- timer
- AGENTS/concurrency::timer
- AGENTS/concurrency::timer::timer
- AGENTS/concurrency::timer::pause
- AGENTS/concurrency::timer::start
- AGENTS/concurrency::timer::stop
- AGENTS/concurrency::timer::accept_message
- AGENTS/concurrency::timer::consume_message
- AGENTS/concurrency::timer::link_target_notification
- AGENTS/concurrency::timer::propagate_to_any_targets
- AGENTS/concurrency::timer::release_message
- AGENTS/concurrency::timer::reserve_message
- AGENTS/concurrency::timer::resume_propagation
dev_langs:
- C++
helpviewer_keywords:
- timer class
ms.assetid: 4f4dea51-de9f-40f9-93f5-dd724c567b49
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b5263c8bf156f190ba5572eacd8ff327be5e3f7a
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="timer-class"></a>Класс timer
Блок обмена сообщениями `timer` — это блок `source_block` с одной целью, который может отправлять сообщение своей цели по истечении указанного периода времени или через заданные интервалы времени.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>
class timer : public Concurrency::details::_Timer, public source_block<single_link_registry<ITarget<T>>>;
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип полезных данных выходных сообщений этого блока.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[timer](#ctor)|Перегружен. Создает `timer` блока обмена сообщениями, который будет отправлять заданное сообщение после указанного интервала.|  
|[~ timer деструктор](#dtor)|Уничтожает `timer` блока обмена сообщениями.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[pause](#pause)|Останавливает `timer` блока обмена сообщениями. Если это повторяющееся `timer` блоке сообщений, ее можно перезапустить с последующем `start()` вызова. — Для неповторяющихся таймеров, это имеет тот же эффект, как `stop` вызова.|  
|[start](#start)|Запускает `timer` блока обмена сообщениями. Указанное число миллисекунд после этого вызова, указанное значение будет распространяться подчиненных как `message`.|  
|[stop](#stop)|Останавливает `timer` блока обмена сообщениями.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[accept_message](#accept_message)|Принимает сообщение, которое было предложено это `timer` блока обмена сообщениями, передавая владение вызывающему объекту.|  
|[consume_message](#consume_message)|Получает сообщение, ранее предложенное `timer` и зарезервированные целевым объектом, передавая владение вызывающему объекту.|  
|[link_target_notification](#link_target_notification)|Обратный вызов, уведомляющее о том, что новый целевой объект был связан это `timer` блока обмена сообщениями.|  
|[propagate_to_any_targets](#propagate_to_any_targets)|Пытается предложить сообщение, созданное с `timer` блок ко всем связанным целевым объектам.|  
|[release_message](#release_message)|Освобождает предыдущее резервирование сообщения. (Переопределяет [source_block::release_message](source-block-class.md#release_message).)|  
|[reserve_message](#reserve_message)|Резервирует сообщение, которое было предложено это `timer` блока обмена сообщениями. (Переопределяет [source_block::reserve_message](source-block-class.md#reserve_message).)|  
|[resume_propagation](#resume_propagation)|Возобновляет распространение после выпуска резервирования. (Переопределяет [source_block::resume_propagation](source-block-class.md#resume_propagation).)|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [ISource](isource-class.md)  
  
 [source_block](source-block-class.md)  
  
 `timer`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="accept_message"></a> accept_message 

 Принимает сообщение, которое было предложено это `timer` блока обмена сообщениями, передавая владение вызывающему объекту.  
  
```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из предложенных `message` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `message` объект, вызывающий теперь принадлежит.  
  
##  <a name="consume_message"></a> consume_message 

 Получает сообщение, ранее предложенное `timer` и зарезервированные целевым объектом, передавая владение вызывающему объекту.  
  
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
  
##  <a name="link_target_notification"></a> link_target_notification 

 Обратный вызов, уведомляющее о том, что новый целевой объект был связан это `timer` блока обмена сообщениями.  
  
```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на только что привязанный целевой объект.  
  
##  <a name="pause"></a> Приостановка 

 Останавливает `timer` блока обмена сообщениями. Если это повторяющееся `timer` блоке сообщений, ее можно перезапустить с последующем `start()` вызова. — Для неповторяющихся таймеров, это имеет тот же эффект, как `stop` вызова.  
  
```
void pause();
```  
  
##  <a name="propagate_to_any_targets"></a> propagate_to_any_targets 

 Пытается предложить сообщение, созданное с `timer` блок ко всем связанным целевым объектам.  
  
```
virtual void propagate_to_any_targets(_Inout_opt_ message<T> *);
```  
  
##  <a name="release_message"></a> release_message 

 Освобождает предыдущее резервирование сообщения.  
  
```
virtual void release_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из `message` объекта освобождение.  
  
##  <a name="reserve_message"></a> reserve_message 

 Резервирует сообщение, которое было предложено это `timer` блока обмена сообщениями.  
  
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
  
##  <a name="start"></a> Запуск 

 Запускает `timer` блока обмена сообщениями. Указанное число миллисекунд после этого вызова, указанное значение будет распространяться подчиненных как `message`.  
  
```
void start();
```  
  
##  <a name="stop"></a> Остановить 

 Останавливает `timer` блока обмена сообщениями.  
  
```
void stop();
```  
  
##  <a name="ctor"></a> Таймера 

 Создает `timer` блока обмена сообщениями, который будет отправлять заданное сообщение после указанного интервала.  
  
```
timer(
    unsigned int _Ms,
    T const& value,
    ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);

timer(
    Scheduler& _Scheduler,
    unsigned int _Ms,
    T const& value,
    _Inout_opt_ ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);

timer(
    ScheduleGroup& _ScheduleGroup,
    unsigned int _Ms,
    T const& value,
    _Inout_opt_ ITarget<T>* _PTarget = NULL,
    bool _Repeating = false);
```  
  
### <a name="parameters"></a>Параметры  
 `_Ms`  
 Число миллисекунд, которое должно пройти после вызова для запуска для указанного сообщения распространялись на более низком уровне.  
  
 `value`  
 Значение, которое будет распространяться более низком уровне, по истечении таймера.  
  
 `_PTarget`  
 Целевой объект, к которому таймер распространяет его сообщение.  
  
 `_Repeating`  
 Значение true указывает, что таймер будет срабатывать периодически каждый `_Ms` миллисекунд.  
  
 `_Scheduler`  
 `Scheduler` Объекта, в течение которого задача распространения для `timer` блока обмена сообщениями запланирована запланирована.  
  
 `_ScheduleGroup`  
 `ScheduleGroup` Объекта, в течение которого задача распространения для `timer` запланирована блока обмена сообщениями. Используемый объект `Scheduler` подразумевается группой расписаний.  
  
### <a name="remarks"></a>Примечания  
 Среда выполнения использует планировщик по умолчанию, если вы не укажете `_Scheduler` или `_ScheduleGroup` параметров.  
  
##  <a name="dtor"></a> ~ timer 

 Уничтожает `timer` блока обмена сообщениями.  
  
```
~timer();
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)
