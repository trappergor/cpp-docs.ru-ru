---
title: "Класс ISource | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ISource
- AGENTS/concurrency::ISource
- AGENTS/concurrency::ISource::accept
- AGENTS/concurrency::ISource::acquire_ref
- AGENTS/concurrency::ISource::consume
- AGENTS/concurrency::ISource::link_target
- AGENTS/concurrency::ISource::release
- AGENTS/concurrency::ISource::release_ref
- AGENTS/concurrency::ISource::reserve
- AGENTS/concurrency::ISource::unlink_target
- AGENTS/concurrency::ISource::unlink_targets
dev_langs:
- C++
helpviewer_keywords:
- ISource class
ms.assetid: c7b73463-42f6-4dcc-801a-81379b12d35a
caps.latest.revision: 20
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: b5545f666dccb251152dc6c9a83101662848be1c
ms.lasthandoff: 03/17/2017

---
# <a name="isource-class"></a>Класс ISource
Класс `ISource` является интерфейсом для всех блоков источников. Блоки источников распространяют сообщения в блоки `ITarget`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>
class ISource;
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных полезных данных внутри сообщений, создаваемых исходным блоком.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`source_type`|Псевдоним для `T`.|  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[~ Деструктор ISource](#dtor)|Уничтожает `ISource` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[принять](#accept)|При переопределении в производном классе, принимает сообщение, предложенное это `ISource` блоком, передавая владение вызывающему объекту.|  
|[acquire_ref](#acquire_ref)|При переопределении в производном классе получает значение счетчика ссылок на это `ISource` блок, чтобы предотвратить удаление.|  
|[Использование](#consume)|При переопределении в производном классе получает сообщение было предложено это `ISource` блока и успешно зарезервированное целевым объектом, передавая владение вызывающему объекту.|  
|[link_target](#link_target)|При переопределении в производном классе связывает целевой блок это `ISource` блок.|  
|[release](#release)|При переопределении в производном классе освобождает предыдущее успешное резервирование сообщения.|  
|[release_ref](#release_ref)|При переопределении в производном классе освобождает значение счетчика ссылок на это `ISource` блок.|  
|[reserve](#reserve)|При переопределении в производном классе резервирует сообщение, которое было предложено это `ISource` блок.|  
|[unlink_target](#unlink_target)|При переопределении в производном классе удаляет связь целевого блока с это `ISource` блокировать, если найден связываемых ранее.|  
|[unlink_targets](#unlink_targets)|При переопределении в производном классе удаляет связь всех целевых блоков от этого `ISource` блок.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ISource`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="accept"></a>принять 

 При переопределении в производном классе, принимает сообщение, предложенное это `ISource` блоком, передавая владение вызывающему объекту.  
  
```
virtual message<T>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из предложенных `message` объекта.  
  
 `_PTarget`  
 Указатель на целевой блок, вызывающий `accept` метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на сообщение, которое теперь принадлежит вызывающей стороне.  
  
### <a name="remarks"></a>Примечания  
 `accept` Метод вызывается целевой объект, пока сообщение предлагается это `ISource` блок. Сообщение указатель, возвращенный может отличаться от того, переданные в `propagate` метод `ITarget` блокировать, если этот источник решает создать копию сообщения.  
  
##  <a name="acquire_ref"></a>acquire_ref 

 При переопределении в производном классе получает значение счетчика ссылок на это `ISource` блок, чтобы предотвратить удаление.  
  
```
virtual void acquire_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на целевой блок, вызывающий этот метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается методом `ITarget` объекта, который связан с этим источником во время `link_target` метод.  
  
##  <a name="consume"></a>Использование 

 При переопределении в производном классе получает сообщение было предложено это `ISource` блока и успешно зарезервированное целевым объектом, передавая владение вызывающему объекту.  
  
```
virtual message<T>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
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
  
##  <a name="dtor"></a>~ ISource 

 Уничтожает `ISource` объекта.  
  
```
virtual ~ISource();
```  
  
##  <a name="link_target"></a>link_target 

 При переопределении в производном классе связывает целевой блок это `ISource` блок.  
  
```
virtual void link_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на целевой блок, связываемый с это `ISource` блок.  
  
##  <a name="release"></a>выпуск 

 При переопределении в производном классе освобождает предыдущее успешное резервирование сообщения.  
  
```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Зарезервированных `message` объекта.  
  
 `_PTarget`  
 Указатель на целевой блок, вызывающий `release` метод.  
  
##  <a name="release_ref"></a>release_ref 

 При переопределении в производном классе освобождает значение счетчика ссылок на это `ISource` блок.  
  
```
virtual void release_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на целевой блок, вызывающий этот метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается методом `ITarget` объект, который является, связь которого с этим источником. Блок источника может освободить ресурсы, зарезервированные для целевой блок.  
  
##  <a name="reserve"></a>Резерв 

 При переопределении в производном классе резервирует сообщение, которое было предложено это `ISource` блок.  
  
```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_MsgId`  
 `runtime_object_identity` Из предложенных `message` объекта.  
  
 `_PTarget`  
 Указатель на целевой блок, вызывающий `reserve` метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true`Если сообщение было успешно зарезервированы, `false` в противном случае. Резервирования могут завершаться неудачей по ряду причин, включая следующие: сообщение уже было зарезервировано или принято другим целевым объектом, источник может отклонять резервирования и т. п.  
  
### <a name="remarks"></a>Примечания  
 После вызова метода `reserve`, если он завершается успешно, необходимо вызвать либо `consume` или `release` чтобы принять или высвободить владение сообщением, соответственно.  
  
##  <a name="unlink_target"></a>unlink_target 

 При переопределении в производном классе удаляет связь целевого блока с это `ISource` блокировать, если найден связываемых ранее.  
  
```
virtual void unlink_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на целевой блок, связь которого с этого `ISource` блок.  
  
##  <a name="unlink_targets"></a>unlink_targets 

 При переопределении в производном классе удаляет связь всех целевых блоков от этого `ISource` блок.  
  
```
virtual void unlink_targets() = 0;
```  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс ITarget](itarget-class.md)

