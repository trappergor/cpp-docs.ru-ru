---
title: "Класс message_processor | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- agents/concurrency::message_processor
dev_langs:
- C++
helpviewer_keywords:
- message_processor class
ms.assetid: 23afb052-daa7-44ed-bf24-d2513db748da
caps.latest.revision: 16
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
ms.openlocfilehash: 98f1c1072916c4cf3670e40ce0c6ddd1a17f1b63
ms.lasthandoff: 02/24/2017

---
# <a name="messageprocessor-class"></a>Класс message_processor
Класс `message_processor` — это абстрактный базовый класс для обработки объектов `message`. Упорядочивание сообщений не гарантируется.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>
class message_processor;
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип данных полезных данных внутри сообщений обрабатываемые этим `message_processor` объекта.  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`type`|Псевдоним для `T`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[async_send метод](#async_send)|При переопределении в производном классе размещает сообщения в блок асинхронно.|  
|[sync_send метод](#sync_send)|При переопределении в производном классе размещает сообщения в блок синхронно.|  
|[wait-метод](#wait)|При переопределении в производном классе, ожидает завершения всех асинхронных операций.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[process_incoming_message метод](#process_incoming_message)|При переопределении в производном классе выполняет прямую обработки сообщений в блок. Один раз, каждый раз добавляется новое сообщение и очередь оказывается пустой.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `message_processor`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-nameasyncsenda-asyncsend"></a><a name="async_send"></a>async_send 

 При переопределении в производном классе размещает сообщения в блок асинхронно.  
  
```
virtual void async_send(_Inout_opt_ message<T>* _Msg) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_Msg`  
 A `message` объекта для асинхронной передачи.  
  
### <a name="remarks"></a>Примечания  
 Этот метод необходимо переопределить в реализации обработчика.  
  
##  <a name="a-nameprocessincomingmessagea-processincomingmessage"></a><a name="process_incoming_message"></a>process_incoming_message 

 При переопределении в производном классе выполняет прямую обработки сообщений в блок. Один раз, каждый раз добавляется новое сообщение и очередь оказывается пустой.  
  
```
virtual void process_incoming_message() = 0;
```  
  
### <a name="remarks"></a>Примечания  
 Реализации блоков сообщений должны переопределять этот метод.  
  
##  <a name="a-namesyncsenda-syncsend"></a><a name="sync_send"></a>sync_send 

 При переопределении в производном классе размещает сообщения в блок синхронно.  
  
```
virtual void sync_send(_Inout_opt_ message<T>* _Msg) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_Msg`  
 Объект `message` объект для отправки в синхронном режиме.  
  
### <a name="remarks"></a>Примечания  
 Этот метод необходимо переопределить в реализации обработчика.  
  
##  <a name="a-namewaita-wait"></a><a name="wait"></a>Ожидание 

 При переопределении в производном классе, ожидает завершения всех асинхронных операций.  
  
```
virtual void wait() = 0;
```  
  
### <a name="remarks"></a>Примечания  
 Этот метод необходимо переопределить в реализации обработчика.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс ordered_message_processor](ordered-message-processor-class.md)

