---
title: "Класс Timer | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::timer
dev_langs:
- C++
helpviewer_keywords:
- timer class
ms.assetid: 4f4dea51-de9f-40f9-93f5-dd724c567b49
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
ms.openlocfilehash: 769ccd051c68f0a4d74511392f0f1a811e36e3e7
ms.lasthandoff: 02/24/2017

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
 Тип полезных данных выводных сообщений этого блока.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор таймера](#ctor)|Перегружен. Создает `timer` блок сообщений, который будет отправлять заданное сообщение после указанного интервала.|  
|[~ таймера деструктор](#dtor)|Уничтожает `timer` блок обмена сообщениями.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Pause-метод](#pause)|Останавливает `timer` блок обмена сообщениями. Если это повторяющееся `timer` блоке сообщений, ее можно перезапустить с последующей `start()` вызова. Для неповторяющихся таймеров, это имеет тот же эффект, как `stop` вызова.|  
|[Start-метод](#start)|Запускает `timer` блок обмена сообщениями. Указанного числа миллисекунд после этого вызова, указанное значение распространяется подчиненной как `message`.|  
|[Метод Stop](#stop)|Останавливает `timer` блок обмена сообщениями.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[accept_message метод](#accept_message)|Принимает сообщение, предложенное это `timer` блок сообщений, передавая владение вызывающему объекту.|  
|[consume_message метод](#consume_message)|Потребляет сообщение, ранее предложенное `timer` и зарезервированное целевым объектом, передавая владение вызывающему объекту.|  
|[link_target_notification метод](#link_target_notification)|Обратный вызов, который уведомляет, что новая цель связана к этому `timer` блок обмена сообщениями.|  
|[propagate_to_any_targets метод](#propagate_to_any_targets)|Пытается предложить сообщение, созданное с `timer` блок ко всем связанным целевым объектам.|  
|[release_message метод](#release_message)|Освобождает предыдущее резервирование сообщения. (Переопределяет [source_block::release_message](source-block-class.md#release_message).)|  
|[reserve_message метод](#reserve_message)|Резервирует сообщение, которое было предложено это `timer` блок обмена сообщениями. (Переопределяет [source_block::reserve_message](source-block-class.md#reserve_message).)|  
|[resume_propagation метод](#resume_propagation)|Возобновляет распространение после выпуска резервирования. (Переопределяет [source_block::resume_propagation](source-block-class.md#resume_propagation).)|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [ISource](isource-class.md)  
  
 [source_block](source-block-class.md)  
  
 `timer`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-nameacceptmessagea-acceptmessage"></a><a name="accept_message"></a>accept_message 

 Принимает сообщение, предложенное это `timer` блок сообщений, передавая владение вызывающему объекту.  
  
```
virtual message<T>* accept_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из предложенных `message` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `message` объект, вызывающий теперь принадлежит.  
  
##  <a name="a-nameconsumemessagea-consumemessage"></a><a name="consume_message"></a>consume_message 

 Потребляет сообщение, ранее предложенное `timer` и зарезервированное целевым объектом, передавая владение вызывающему объекту.  
  
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
  
##  <a name="a-namelinktargetnotificationa-linktargetnotification"></a><a name="link_target_notification"></a>link_target_notification 

 Обратный вызов, который уведомляет, что новая цель связана к этому `timer` блок обмена сообщениями.  
  
```
virtual void link_target_notification(_Inout_ ITarget<T>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на только что привязанный целевой объект.  
  
##  <a name="a-namepausea-pause"></a><a name="pause"></a>Приостановить 

 Останавливает `timer` блок обмена сообщениями. Если это повторяющееся `timer` блоке сообщений, ее можно перезапустить с последующей `start()` вызова. Для неповторяющихся таймеров, это имеет тот же эффект, как `stop` вызова.  
  
```
void pause();
```  
  
##  <a name="a-namepropagatetoanytargetsa-propagatetoanytargets"></a><a name="propagate_to_any_targets"></a>propagate_to_any_targets 

 Пытается предложить сообщение, созданное с `timer` блок ко всем связанным целевым объектам.  
  
```
virtual void propagate_to_any_targets(_Inout_opt_ message<T> *);
```  
  
##  <a name="a-namereleasemessagea-releasemessage"></a><a name="release_message"></a>release_message 

 Освобождает предыдущее резервирование сообщения.  
  
```
virtual void release_message(runtime_object_identity _MsgId);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из `message` объект освобожден.  
  
##  <a name="a-namereservemessagea-reservemessage"></a><a name="reserve_message"></a>reserve_message 

 Резервирует сообщение, которое было предложено это `timer` блок обмена сообщениями.  
  
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
  
##  <a name="a-namestarta-start"></a><a name="start"></a>Запуск 

 Запускает `timer` блок обмена сообщениями. Указанного числа миллисекунд после этого вызова, указанное значение распространяется подчиненной как `message`.  
  
```
void start();
```  
  
##  <a name="a-namestopa-stop"></a><a name="stop"></a>остановить 

 Останавливает `timer` блок обмена сообщениями.  
  
```
void stop();
```  
  
##  <a name="a-namectora-timer"></a><a name="ctor"></a>таймер 

 Создает `timer` блок сообщений, который будет отправлять заданное сообщение после указанного интервала.  
  
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
 Число миллисекунд, которое должно пройти после вызова для запуска для указанного сообщения распространяться на более низком уровне.  
  
 `value`  
 Значение, которое будет распространяться по ходе процесса по истечении таймера.  
  
 `_PTarget`  
 Целевой объект, к которому таймер распространяет его сообщение.  
  
 `_Repeating`  
 Значение true указывает, что таймер будет срабатывать периодически каждые `_Ms` мс.  
  
 `_Scheduler`  
 `Scheduler` Объекта, в течение которого задача распространения `timer` блок сообщений запланирована запланирована.  
  
 `_ScheduleGroup`  
 `ScheduleGroup` Объекта, в течение которого задача распространения `timer` запланирована блок обмена сообщениями. Используемый объект `Scheduler` подразумевается группой расписаний.  
  
### <a name="remarks"></a>Примечания  
 Среда выполнения использует планировщик по умолчанию, если вы не укажете `_Scheduler` или `_ScheduleGroup` параметры.  
  
##  <a name="a-namedtora-timer"></a><a name="dtor"></a>~ timer 

 Уничтожает `timer` блок обмена сообщениями.  
  
```
~timer();
```  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)

