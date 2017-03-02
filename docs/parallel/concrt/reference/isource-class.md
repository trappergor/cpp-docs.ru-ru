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
- agents/concurrency::ISource
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: db3ba296a96b2e77c0ae7d9be3d0a499fe2e7f76
ms.lasthandoff: 02/24/2017

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
|[Accept-метод](#accept)|При переопределении в производном классе, принимает сообщение, предложенное это `ISource` блоком, передавая владение вызывающему объекту.|  
|[acquire_ref метод](#acquire_ref)|При переопределении в производном классе получает значение счетчика ссылок на это `ISource` блок, чтобы предотвратить удаление.|  
|[consume-метод](#consume)|При переопределении в производном классе получает сообщение было предложено это `ISource` блока и успешно зарезервированное целевым объектом, передавая владение вызывающему объекту.|  
|[Метод link_target](#link_target)|При переопределении в производном классе связывает целевой блок это `ISource` блок.|  
|[Release-метод](#release)|При переопределении в производном классе освобождает предыдущее успешное резервирование сообщения.|  
|[release_ref метод](#release_ref)|При переопределении в производном классе освобождает значение счетчика ссылок на это `ISource` блок.|  
|[reserve-метод](#reserve)|При переопределении в производном классе резервирует сообщение, которое было предложено это `ISource` блок.|  
|[unlink_target метод](#unlink_target)|При переопределении в производном классе удаляет связь целевого блока с это `ISource` блокировать, если найден связываемых ранее.|  
|[unlink_targets метод](#unlink_targets)|При переопределении в производном классе удаляет связь всех целевых блоков от этого `ISource` блок.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ISource`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-nameaccepta-accept"></a><a name="accept"></a>принять 

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
  
##  <a name="a-nameacquirerefa-acquireref"></a><a name="acquire_ref"></a>acquire_ref 

 При переопределении в производном классе получает значение счетчика ссылок на это `ISource` блок, чтобы предотвратить удаление.  
  
```
virtual void acquire_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на целевой блок, вызывающий этот метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается методом `ITarget` объекта, который связан с этим источником во время `link_target` метод.  
  
##  <a name="a-nameconsumea-consume"></a><a name="consume"></a>Использование 

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
  
##  <a name="a-namedtora-isource"></a><a name="dtor"></a>~ ISource 

 Уничтожает `ISource` объекта.  
  
```
virtual ~ISource();
```  
  
##  <a name="a-namelinktargeta-linktarget"></a><a name="link_target"></a>link_target 

 При переопределении в производном классе связывает целевой блок это `ISource` блок.  
  
```
virtual void link_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на целевой блок, связываемый с это `ISource` блок.  
  
##  <a name="a-namereleasea-release"></a><a name="release"></a>выпуск 

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
  
##  <a name="a-namereleaserefa-releaseref"></a><a name="release_ref"></a>release_ref 

 При переопределении в производном классе освобождает значение счетчика ссылок на это `ISource` блок.  
  
```
virtual void release_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на целевой блок, вызывающий этот метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается методом `ITarget` объект, который является, связь которого с этим источником. Блок источника может освободить ресурсы, зарезервированные для целевой блок.  
  
##  <a name="a-namereservea-reserve"></a><a name="reserve"></a>Резерв 

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
  
##  <a name="a-nameunlinktargeta-unlinktarget"></a><a name="unlink_target"></a>unlink_target 

 При переопределении в производном классе удаляет связь целевого блока с это `ISource` блокировать, если найден связываемых ранее.  
  
```
virtual void unlink_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_PTarget`  
 Указатель на целевой блок, связь которого с этого `ISource` блок.  
  
##  <a name="a-nameunlinktargetsa-unlinktargets"></a><a name="unlink_targets"></a>unlink_targets 

 При переопределении в производном классе удаляет связь всех целевых блоков от этого `ISource` блок.  
  
```
virtual void unlink_targets() = 0;
```  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс ITarget](itarget-class.md)

