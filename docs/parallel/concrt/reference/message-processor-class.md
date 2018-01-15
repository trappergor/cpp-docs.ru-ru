---
title: "Класс message_processor | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- message_processor
- AGENTS/concurrency::message_processor
- AGENTS/concurrency::message_processor::async_send
- AGENTS/concurrency::message_processor::sync_send
- AGENTS/concurrency::message_processor::wait
- AGENTS/concurrency::message_processor::process_incoming_message
dev_langs: C++
helpviewer_keywords: message_processor class
ms.assetid: 23afb052-daa7-44ed-bf24-d2513db748da
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: b8c2f30bbab85760020c19a25b098b31eb0a8893
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|`type`|Псевдоним для `T`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[async_send](#async_send)|При переопределении в производном классе размещает сообщения в блок асинхронно.|  
|[sync_send](#sync_send)|При переопределении в производном классе размещает сообщения в блок синхронно.|  
|[Ожидание](#wait)|При переопределении в производном классе, ожидает завершения всех асинхронных операций.|  
  
### <a name="protected-methods"></a>Защищенные методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[process_incoming_message](#process_incoming_message)|При переопределении в производном классе выполняет прямую обработки сообщений в блок. Вызывается один раз, каждый раз, добавляется новое сообщение и очередь оказывается пустой.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `message_processor`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** agents.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="async_send"></a>async_send 

 При переопределении в производном классе размещает сообщения в блок асинхронно.  
  
```
virtual void async_send(_Inout_opt_ message<T>* _Msg) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_Msg`  
 Объект `message` объект отправлять в асинхронном режиме.  
  
### <a name="remarks"></a>Примечания  
 Процессор реализации должны переопределять этот метод.  
  
##  <a name="process_incoming_message"></a>process_incoming_message 

 При переопределении в производном классе выполняет прямую обработки сообщений в блок. Вызывается один раз, каждый раз, добавляется новое сообщение и очередь оказывается пустой.  
  
```
virtual void process_incoming_message() = 0;
```  
  
### <a name="remarks"></a>Примечания  
 Реализации блоков сообщений должны переопределять этот метод.  
  
##  <a name="sync_send"></a>sync_send 

 При переопределении в производном классе размещает сообщения в блок синхронно.  
  
```
virtual void sync_send(_Inout_opt_ message<T>* _Msg) = 0;
```  
  
### <a name="parameters"></a>Параметры  
 `_Msg`  
 Объект `message` объект для отправки в синхронном режиме.  
  
### <a name="remarks"></a>Примечания  
 Процессор реализации должны переопределять этот метод.  
  
##  <a name="wait"></a>Ожидание 

 При переопределении в производном классе, ожидает завершения всех асинхронных операций.  
  
```
virtual void wait() = 0;
```  
  
### <a name="remarks"></a>Примечания  
 Процессор реализации должны переопределять этот метод.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс ordered_message_processor](ordered-message-processor-class.md)
