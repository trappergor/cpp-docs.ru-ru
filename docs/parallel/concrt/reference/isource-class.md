---
title: Класс ISource | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 14593161512e56d39b77bb0cc5af88a3ff849409
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46071891"
---
# <a name="isource-class"></a>Класс ISource
Класс `ISource` является интерфейсом для всех блоков источников. Блоки источников распространяют сообщения в блоки `ITarget`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>
class ISource;
```  
  
#### <a name="parameters"></a>Параметры  
*T*<br/>
Тип полезных данных в сообщения, созданные блок источника данных.  
  
## <a name="members"></a>Участники  
  
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
|[Принять](#accept)|При переопределении в производном классе, принимает сообщение, предложенное это `ISource` блоком, передавая владение вызывающему объекту.|  
|[acquire_ref](#acquire_ref)|При переопределении в производном классе получает значение счетчика ссылок на это `ISource` блок, чтобы предотвратить удаление данных.|  
|[Использование](#consume)|При переопределении в производном классе, получает сообщение, ранее предложенного этим объектом `ISource` блокировать и успешно зарезервированное целевым объектом, передавая владение вызывающему объекту.|  
|[link_target](#link_target)|При переопределении в производном классе связывает целевой блок это `ISource` блока.|  
|[release](#release)|При переопределении в производном классе освобождает предыдущее резервирование сообщение об успешной.|  
|[release_ref](#release_ref)|При переопределении в производном классе освобождает значение счетчика ссылок на это `ISource` блока.|  
|[reserve](#reserve)|При переопределении в производном классе резервирует сообщение, ранее предложенного этим объектом `ISource` блока.|  
|[unlink_target](#unlink_target)|При переопределении в производном классе удаляет связь целевым блоком и это `ISource` заблокировать, если найден связываться ранее.|  
|[unlink_targets](#unlink_targets)|При переопределении в производном классе удаляет связь всех целевых блоков из этого `ISource` блока.|  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ISource`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="accept"></a> Принять 

 При переопределении в производном классе, принимает сообщение, предложенное это `ISource` блоком, передавая владение вызывающему объекту.  
  
```
virtual message<T>* accept(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Параметры  
*_MsgId*<br/>
`runtime_object_identity` Из предложенные `message` объекта.  
  
*_PTarget*<br/>
Указатель на целевой блок, который вызывает `accept` метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на сообщение, которое теперь принадлежит вызывающий объект.  
  
### <a name="remarks"></a>Примечания  
 `accept` Метод вызывается целевого объекта, пока сообщение предлагается это `ISource` блока. Для сообщения возвращаемого указателя может отличаться от тот, который передается в `propagate` метод `ITarget` заблокировать, если этот источник решает создать копию сообщения.  
  
##  <a name="acquire_ref"></a> acquire_ref 

 При переопределении в производном классе получает значение счетчика ссылок на это `ISource` блок, чтобы предотвратить удаление данных.  
  
```
virtual void acquire_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Параметры  
*_PTarget*<br/>
Указатель на целевой блок, который вызывает этот метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается `ITarget` объект, который, связанным с данного источника во время `link_target` метод.  
  
##  <a name="consume"></a> Использование 

 При переопределении в производном классе, получает сообщение, ранее предложенного этим объектом `ISource` блокировать и успешно зарезервированное целевым объектом, передавая владение вызывающему объекту.  
  
```
virtual message<T>* consume(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Параметры  
*_MsgId*<br/>
`runtime_object_identity` Зарезервированных `message` объекта.  
  
*_PTarget*<br/>
Указатель на целевой блок, который вызывает `consume` метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `message` объекта, что вызывающий объект теперь принадлежит.  
  
### <a name="remarks"></a>Примечания  
 `consume` Метод аналогичен методу `accept`, но всегда должно начинаться с помощью вызова `reserve` , возвращается `true`.  
  
##  <a name="dtor"></a> ~ ISource 

 Уничтожает `ISource` объекта.  
  
```
virtual ~ISource();
```  
  
##  <a name="link_target"></a> link_target 

 При переопределении в производном классе связывает целевой блок это `ISource` блока.  
  
```
virtual void link_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Параметры  
*_PTarget*<br/>
Указатель на целевой блок, связываемый с это `ISource` блока.  
  
##  <a name="release"></a> выпуск 

 При переопределении в производном классе освобождает предыдущее резервирование сообщение об успешной.  
  
```
virtual void release(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Параметры  
*_MsgId*<br/>
`runtime_object_identity` Зарезервированных `message` объекта.  
  
*_PTarget*<br/>
Указатель на целевой блок, который вызывает `release` метод.  
  
##  <a name="release_ref"></a> release_ref 

 При переопределении в производном классе освобождает значение счетчика ссылок на это `ISource` блока.  
  
```
virtual void release_ref(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Параметры  
*_PTarget*<br/>
Указатель на целевой блок, который вызывает этот метод.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывается `ITarget` объект, который является, связь которого с данного источника. Блок источника может освободить все ресурсы, зарезервированные для целевой блок.  
  
##  <a name="reserve"></a> Резерв 

 При переопределении в производном классе резервирует сообщение, ранее предложенного этим объектом `ISource` блока.  
  
```
virtual bool reserve(
    runtime_object_identity _MsgId,
    _Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Параметры  
*_MsgId*<br/>
`runtime_object_identity` Из предложенные `message` объекта.  
  
*_PTarget*<br/>
Указатель на целевой блок, который вызывает `reserve` метод.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `true` Если сообщение было успешно зарезервировано, `false` в противном случае. Резервирования могут завершаться неудачей по ряду причин, включая следующие: сообщение уже было зарезервировано или принято другим целевым объектом, источник может отклонять резервирования и т. п.  
  
### <a name="remarks"></a>Примечания  
 После вызова метода `reserve`, если он завершается успешно, следует вызвать `consume` или `release` чтобы принять или высвободить владение сообщением, соответственно.  
  
##  <a name="unlink_target"></a> unlink_target 

 При переопределении в производном классе удаляет связь целевым блоком и это `ISource` заблокировать, если найден связываться ранее.  
  
```
virtual void unlink_target(_Inout_ ITarget<T>* _PTarget) = 0;
```  
  
### <a name="parameters"></a>Параметры  
*_PTarget*<br/>
Указатель на целевой блок, связь которого с это `ISource` блока.  
  
##  <a name="unlink_targets"></a> unlink_targets 

 При переопределении в производном классе удаляет связь всех целевых блоков из этого `ISource` блока.  
  
```
virtual void unlink_targets() = 0;
```  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс ITarget](itarget-class.md)
