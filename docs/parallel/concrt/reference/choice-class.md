---
title: "Класс Choice | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 13110f3a221be47716ca60618c59d2e4bdd6911e
ms.contentlocale: ru-ru
ms.lasthandoff: 03/17/2017

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
 A `tuple`-на основе типа, представляющий полезные нагрузки входных источников.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`type`|Псевдоним для `T`.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Выбор](#ctor)|Перегружен. Создает блок обмена сообщениями `choice` .|  
|[~ choice деструктор](#dtor)|Уничтожает `choice` блок обмена сообщениями.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[принять](#accept)|Принимает сообщение, предложенное это `choice` блоком, передавая владение вызывающему объекту.|  
|[acquire_ref](#acquire_ref)|Получает значение счетчика ссылок на это `choice` блок сообщений, чтобы предотвратить удаление.|  
|[Использование](#consume)|Потребляет сообщение, ранее предложенное это `choice` блок обмена сообщениями и успешно зарезервированное целевым объектом, передавая владение вызывающему объекту.|  
|[has_value](#has_value)|Проверяет, является ли это `choice` блок сообщений еще инициализирован со значением.|  
|[Индекс](#index)|Возвращает индекс в `tuple` представляет элемент, выбранный по `choice` блок обмена сообщениями.|  
|[link_target](#link_target)|Это связывает целевой блок `choice` блок обмена сообщениями.|  
|[release](#release)|Освобождает предыдущее успешное резервирование сообщения.|  
|[release_ref](#release_ref)|Освобождает значение счетчика ссылок на это `choice` блок обмена сообщениями.|  
|[reserve](#reserve)|Резервирует сообщение, которое было предложено это `choice` блок обмена сообщениями.|  
|[unlink_target](#unlink_target)|Удаляет связь целевого блока с это `choice` блок обмена сообщениями.|  
|[unlink_targets](#unlink_targets)|Удаляет связь всех целевых объектов из этого `choice` блок обмена сообщениями. (Переопределяет [ISource::unlink_targets](isource-class.md#unlink_targets).)|  
|[value](#value)|Получает сообщение, индекс которого был выбран, `choice` блок обмена сообщениями.|  
  
## <a name="remarks"></a>Примечания  
 Блок выбора гарантирует, что используется только одно из входящих сообщений.  
  
 Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [ISource](isource-class.md)  
  
 `choice`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="accept"></a>принять 

 Принимает сообщение, предложенное это `choice` блоком, передавая владение вызывающему объекту.  
  
```  
virtual message<size_t>* accept(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из предложенных `message` объекта.  
  
 `_PTarget`  
 Указатель на целевой блок, вызывающий `accept` метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на сообщение, которое теперь принадлежит вызывающей стороне.  
  
##  <a name="acquire_ref"></a>acquire_ref 

 Получает значение счетчика ссылок на это `choice` блок сообщений, чтобы предотвратить удаление.  
  
```  
virtual void acquire_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на целевой блок, вызывающий этот метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается методом `ITarget` объекта, который связан с этим источником во время `link_target` метод.  
  
##  <a name="ctor"></a>Выбор 

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
  
##  <a name="dtor"></a>~ choice 

 Уничтожает `choice` блок обмена сообщениями.  
  
```  
~choice();
```  
  
##  <a name="consume"></a>Использование 

 Потребляет сообщение, ранее предложенное это `choice` блок обмена сообщениями и успешно зарезервированное целевым объектом, передавая владение вызывающему объекту.  
  
```  
virtual message<size_t>* consume(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Зарезервированных `message` объекта.  
  
 `_PTarget`  
 Указатель на целевой блок, вызывающий `consume` метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `message` объект, вызывающий теперь принадлежит.  
  
### <a name="remarks"></a>Примечания  
 `consume` Метод аналогичен `accept`, но всегда должно начинаться с помощью вызова `reserve` , возвращается `true`.  
  
##  <a name="has_value"></a>has_value 

 Проверяет, является ли это `choice` блок сообщений еще инициализирован со значением.  
  
```  
bool has_value() const;

 
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если блок получил значение, `false` в противном случае.  
  
##  <a name="index"></a>Индекс 

 Возвращает индекс в `tuple` представляет элемент, выбранный по `choice` блок обмена сообщениями.  
  
```  
size_t index();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Индекс сообщения.  
  
### <a name="remarks"></a>Примечания  
 Полезные данные сообщения могут быть извлечены с помощью `get` метод.  
  
##  <a name="link_target"></a>link_target 

 Это связывает целевой блок `choice` блок обмена сообщениями.  
  
```  
virtual void link_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на `ITarget` блок, чтобы создать ссылку на этот `choice` блок обмена сообщениями.  
  
##  <a name="release"></a>выпуск 

 Освобождает предыдущее успешное резервирование сообщения.  
  
```  
virtual void release(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из `message` объект освобожден.  
  
 `_PTarget`  
 Указатель на целевой блок, вызывающий `release` метод.  
  
##  <a name="release_ref"></a>release_ref 

 Освобождает значение счетчика ссылок на это `choice` блок обмена сообщениями.  
  
```  
virtual void release_ref(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на целевой блок, вызывающий этот метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается методом `ITarget` объект, который является, связь которого с этим источником. Блок источника может освободить ресурсы, зарезервированные для целевой блок.  
  
##  <a name="reserve"></a>Резерв 

 Резервирует сообщение, которое было предложено это `choice` блок обмена сообщениями.  
  
```  
virtual bool reserve(
    runtime_object_identity _MsgId,  
    _Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из `message` объекта резервируются.  
  
 `_PTarget`  
 Указатель на целевой блок, вызывающий `reserve` метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если сообщение было успешно зарезервированы, `false` в противном случае. Резервирования могут завершаться неудачей по ряду причин, включая следующие: сообщение уже было зарезервировано или принято другим целевым объектом, источник может отклонять резервирования и т. п.  
  
### <a name="remarks"></a>Примечания  
 После вызова метода `reserve`, если он завершается успешно, необходимо вызвать либо `consume` или `release` чтобы принять или высвободить владение сообщением, соответственно.  
  
##  <a name="unlink_target"></a>unlink_target 

 Удаляет связь целевого блока с это `choice` блок обмена сообщениями.  
  
```  
virtual void unlink_target(_Inout_ ITarget<size_t>* _PTarget);
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на `ITarget` блок отсоединиться от этого `choice` блок обмена сообщениями.  
  
##  <a name="unlink_targets"></a>unlink_targets 

 Удаляет связь всех целевых объектов из этого `choice` блок обмена сообщениями.  
  
```  
virtual void unlink_targets();
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод не вызывается из деструктора, поскольку деструктор для внутреннего `single_assignment` блок будет разрывать связь правильно.  
  
##  <a name="value"></a>значение 

 Получает сообщение, индекс которого был выбран, `choice` блок обмена сообщениями.  
  
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

