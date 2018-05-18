---
title: Класс Choice | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- choice
- AGENTS/concurrency::choice
- AGENTS/concurrency::choice::choice
- AGENTS/concurrency::choice::accept
- AGENTS/concurrency::choice::acquire_ref
- AGENTS/concurrency::choice::consume
- AGENTS/concurrency::choice::has_value
- AGENTS/concurrency::choice::index
- AGENTS/concurrency::choice::link_target
- AGENTS/concurrency::choice::release
- AGENTS/concurrency::choice::release_ref
- AGENTS/concurrency::choice::reserve
- AGENTS/concurrency::choice::unlink_target
- AGENTS/concurrency::choice::unlink_targets
- AGENTS/concurrency::choice::value
dev_langs:
- C++
helpviewer_keywords:
- choice class
ms.assetid: 4157a539-d5c2-4161-b1ab-536ce2888397
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 56b936e1ecb3864b7a7bb95f3e552c16d2ce81d0
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
---
# <a name="choice-class"></a>Класс choice
Блок обмена сообщениями `choice` — это блок с несколькими источниками и одной целью, который представляет взаимодействие потока управления с набором источников. Блок choice будет ожидать доступа к любому из нескольких источников для создания сообщения и распространит индекс источника, создавшего сообщение.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<
    class T  
>  
class choice: public ISource<size_t>;  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 A `tuple`-тип, представляющий полезные данные из источников входных данных, основанный на.  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`type`|Псевдоним для `T`.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Выбор](#ctor)|Перегружен. Создает блок обмена сообщениями `choice` .|  
|[~ choice деструктор](#dtor)|Уничтожает `choice` блока обмена сообщениями.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Принять](#accept)|Принимает сообщение, которое было предложено это `choice` блоком, передавая владение вызывающему объекту.|  
|[acquire_ref](#acquire_ref)|Получает значение счетчика ссылок на это `choice` блока обмена сообщениями, чтобы предотвратить удаление.|  
|[Использовать](#consume)|Получает сообщение было предложено это `choice` блок обмена сообщениями и успешно зарезервированное целевым объектом, передавая владение вызывающему объекту.|  
|[has_value](#has_value)|Проверяет, является ли это `choice` блока обмена сообщениями еще была инициализирована со значением.|  
|[Индекс](#index)|Возвращает индекс в `tuple` представляет элемент, выбранный по `choice` блока обмена сообщениями.|  
|[link_target](#link_target)|Ссылки на это целевой блок `choice` блока обмена сообщениями.|  
|[release](#release)|Освобождает предыдущее успешное резервирование сообщения.|  
|[release_ref](#release_ref)|Освобождает значение счетчика ссылок на это `choice` блока обмена сообщениями.|  
|[reserve](#reserve)|Резервирует сообщение, которое было предложено это `choice` блока обмена сообщениями.|  
|[unlink_target](#unlink_target)|Удаляет связь из этого блока целевого `choice` блока обмена сообщениями.|  
|[unlink_targets](#unlink_targets)|Удаляет связь все целевые объекты из этого `choice` блока обмена сообщениями. (Переопределяет [ISource::unlink_targets](isource-class.md#unlink_targets).)|  
|[value](#value)|Получает сообщение, индекс которого был выбран, `choice` блока обмена сообщениями.|  
  
## <a name="remarks"></a>Примечания  
 Блок выбора гарантирует, что только один из входящих сообщений использованы.  
  
 Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [ISource](isource-class.md)  
  
 `choice`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="accept"></a> Принять 

 Принимает сообщение, которое было предложено это `choice` блоком, передавая владение вызывающему объекту.  
  
```  
virtual message<size_t>* accept(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из предложенных `message` объекта.  
  
 `_PTarget`  
 Указатель на целевой блок, который вызывает `accept` метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на сообщение, которое теперь принадлежит вызывающей стороне.  
  
##  <a name="acquire_ref"></a> acquire_ref 

 Получает значение счетчика ссылок на это `choice` блока обмена сообщениями, чтобы предотвратить удаление.  
  
```  
virtual void acquire_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на целевой блок, вызывающий этот метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается методом `ITarget` объекту, связанному этого источника во время `link_target` метод.  
  
##  <a name="ctor"></a> Выбор 

 Создает блок обмена сообщениями `choice` .  
  
```  
explicit choice(
    T _Tuple);

 
choice(
    Scheduler& _PScheduler,  
    T _Tuple);

 
choice(
    ScheduleGroup& _PScheduleGroup,  
    T _Tuple);

 
choice(
    choice&& _Choice);
```  
  
### <a name="parameters"></a>Параметры  
 `_Tuple`  
 Объект `tuple` источников по выбору.  
  
 `_PScheduler`  
 Объект `Scheduler` , в котором запланирована задача распространения для блока обмена сообщениями `choice` .  
  
 `_PScheduleGroup`  
 Объект `ScheduleGroup` , в котором запланирована задача распространения для блока обмена сообщениями `choice` . Используемый объект `Scheduler` подразумевается группой расписаний.  
  
 `_Choice`  
 Блок обмена сообщениями `choice` , из которого выполняется копирование. Обратите внимание, что исходный объект становится потерянным, превращая этот конструктор в конструктор перемещения.  
  
### <a name="remarks"></a>Примечания  
 Среда выполнения использует планировщик по умолчанию, если вы не указали параметры `_PScheduler` или `_PScheduleGroup` .  
  
 Конструкция перемещения не выполняется при блокировке. Это означает, что пользователь должен убедиться в отсутствии простых задач во время перемещения. В противном случае могут возникнуть многочисленные гонки, приводящие к исключениям или недопустимому состоянию.  
  
##  <a name="dtor"></a> ~ выбора 

 Уничтожает `choice` блока обмена сообщениями.  
  
```  
~choice();
```  
  
##  <a name="consume"></a> Использовать 

 Получает сообщение было предложено это `choice` блок обмена сообщениями и успешно зарезервированное целевым объектом, передавая владение вызывающему объекту.  
  
```  
virtual message<size_t>* consume(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Зарезервированных `message` объекта.  
  
 `_PTarget`  
 Указатель на целевой блок, который вызывает `consume` метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `message` объект, вызывающий теперь принадлежит.  
  
### <a name="remarks"></a>Примечания  
 `consume` Аналогичен методу `accept`, но всегда должно начинаться с помощью вызова `reserve` , которые вернули `true`.  
  
##  <a name="has_value"></a> has_value 

 Проверяет, является ли это `choice` блока обмена сообщениями еще была инициализирована со значением.  
  
```  
bool has_value() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если блок получил значение, `false` в противном случае.  
  
##  <a name="index"></a> Индекс 

 Возвращает индекс в `tuple` представляет элемент, выбранный по `choice` блока обмена сообщениями.  
  
```  
size_t index();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс сообщения.  
  
### <a name="remarks"></a>Примечания  
 Полезные данные сообщения можно извлечь при помощи `get` метод.  
  
##  <a name="link_target"></a> link_target 

 Ссылки на это целевой блок `choice` блока обмена сообщениями.  
  
```  
virtual void link_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на `ITarget` блок, чтобы создать ссылку на этот `choice` блока обмена сообщениями.  
  
##  <a name="release"></a> выпуск 

 Освобождает предыдущее успешное резервирование сообщения.  
  
```  
virtual void release(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из `message` объекта освобождение.  
  
 `_PTarget`  
 Указатель на целевой блок, который вызывает `release` метод.  
  
##  <a name="release_ref"></a> release_ref 

 Освобождает значение счетчика ссылок на это `choice` блока обмена сообщениями.  
  
```  
virtual void release_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на целевой блок, вызывающий этот метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается методом `ITarget` объект, который является, связь которого с этим источником. Блок источника может освободить ресурсы, зарезервированные для целевой блок.  
  
##  <a name="reserve"></a> Резерв 

 Резервирует сообщение, которое было предложено это `choice` блока обмена сообщениями.  
  
```  
virtual bool reserve(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из `message` объекта резервируются.  
  
 `_PTarget`  
 Указатель на целевой блок, который вызывает `reserve` метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если сообщение было успешно зарезервированы, `false` в противном случае. Резервирования могут завершаться неудачей по ряду причин, включая следующие: сообщение уже было зарезервировано или принято другим целевым объектом, источник может отклонять резервирования и т. п.  
  
### <a name="remarks"></a>Примечания  
 После вызова метода `reserve`, если он завершается успешно, следует вызвать `consume` или `release` чтобы принять или высвободить владение сообщением, соответственно.  
  
##  <a name="unlink_target"></a> unlink_target 

 Удаляет связь из этого блока целевого `choice` блока обмена сообщениями.  
  
```  
virtual void unlink_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на `ITarget` блок, чтобы удалить связь из этого `choice` блока обмена сообщениями.  
  
##  <a name="unlink_targets"></a> unlink_targets 

 Удаляет связь все целевые объекты из этого `choice` блока обмена сообщениями.  
  
```  
virtual void unlink_targets();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод не вызывается из деструктора, поскольку деструктор для внутренней `single_assignment` блок будет разрывать связь правильно.  
  
##  <a name="value"></a> Значение 

 Получает сообщение, индекс которого был выбран, `choice` блока обмена сообщениями.  
  
```  
template <
    typename _Payload_type  
>  
_Payload_type const& value();
```  
  
### <a name="parameters"></a>Параметры  
 `_Payload_type`  
 Тип полезных данных сообщения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Полезные данные сообщения.  
  
### <a name="remarks"></a>Примечания  
 Поскольку блок сообщений `choice` может принимать входные данные с различными типами полезной нагрузки, необходимо указать тип полезной нагрузки в момент извлечения. Можно определить тип, основанный на результате `index` метод.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс JOIN](join-class.md)   
 [Класс single_assignment](single-assignment-class.md)
