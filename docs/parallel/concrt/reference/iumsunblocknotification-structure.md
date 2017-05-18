---
title: "Структура IUMSUnblockNotification | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetContext
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetNextUnblockNotification
dev_langs:
- C++
helpviewer_keywords:
- IUMSUnblockNotification structure
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
caps.latest.revision: 19
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
ms.openlocfilehash: ee9c1ada7718b948e5a038852bfa5514127324b1
ms.contentlocale: ru-ru
ms.lasthandoff: 03/17/2017

---
# <a name="iumsunblocknotification-structure"></a>Структура IUMSUnblockNotification
Представляет уведомление диспетчера ресурсов о том, что прокси-поток, который заблокировал и запустил возврат к заданному контексту планирования планировщика, разблокирован и готов для планирования. Этот интерфейс является недопустимым, когда связанный с прокси-потоком контекст выполнения, возвращенный из метода `GetContext`, переносится.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct IUMSUnblockNotification;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[IUMSUnblockNotification::GetContext](#getcontext)|Возвращает `IExecutionContext` интерфейс для контекста выполнения, связанного с прокси-поток, который был разблокирован. Когда этот метод возвращает базовый контекст выполнения будет повторно через вызов `IThreadProxy::SwitchTo` метода, этот интерфейс больше не действительна.|  
|[IUMSUnblockNotification::GetNextUnblockNotification](#getnextunblocknotification)|Возвращает следующий `IUMSUnblockNotification` интерфейс в цепочке, возвращенный методом `IUMSCompletionList::GetUnblockNotifications`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IUMSUnblockNotification`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="getcontext"></a>Метод IUMSUnblockNotification::GetContext  
 Возвращает `IExecutionContext` интерфейс для контекста выполнения, связанного с прокси-поток, который был разблокирован. Когда этот метод возвращает базовый контекст выполнения будет повторно через вызов `IThreadProxy::SwitchTo` метода, этот интерфейс больше не действительна.  
  
```
virtual IExecutionContext* GetContext() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `IExecutionContext` Интерфейс для контекста выполнения потока прокси, который был разблокирован.  
  
##  <a name="getnextunblocknotification"></a>Метод IUMSUnblockNotification::GetNextUnblockNotification  
 Возвращает следующий `IUMSUnblockNotification` интерфейс в цепочке, возвращенный методом `IUMSCompletionList::GetUnblockNotifications`.  
  
```
virtual IUMSUnblockNotification* GetNextUnblockNotification() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Следующий `IUMSUnblockNotification` интерфейс в цепочке, возвращенный методом `IUMSCompletionList::GetUnblockNotifications`.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Структура IUMSScheduler](iumsscheduler-structure.md)   
 [Структура IUMSCompletionList](iumscompletionlist-structure.md)

