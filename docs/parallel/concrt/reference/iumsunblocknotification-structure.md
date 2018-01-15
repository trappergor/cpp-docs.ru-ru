---
title: "Структура IUMSUnblockNotification | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetContext
- CONCRTRM/concurrency::IUMSUnblockNotification::IUMSUnblockNotification::GetNextUnblockNotification
dev_langs: C++
helpviewer_keywords: IUMSUnblockNotification structure
ms.assetid: eaca9529-c1cc-472b-8ec6-722a1ff0fa2a
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3febe10f7c71e1c1d478dd6f6b6f565c4134e033
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="iumsunblocknotification-structure"></a>Структура IUMSUnblockNotification
Представляет уведомление диспетчера ресурсов о том, что прокси-поток, который заблокировал и запустил возврат к заданному контексту планирования планировщика, разблокирован и готов для планирования. Этот интерфейс является недопустимым, когда связанный с прокси-потоком контекст выполнения, возвращенный из метода `GetContext`, переносится.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct IUMSUnblockNotification;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IUMSUnblockNotification::GetContext](#getcontext)|Возвращает `IExecutionContext` интерфейс для контекста выполнения, связанного с прокси-поток, который был разблокирован. Когда этот метод возвращает базовый контекст выполнения поставлена через вызов `IThreadProxy::SwitchTo` метод, этот интерфейс больше не является допустимым.|  
|[IUMSUnblockNotification::GetNextUnblockNotification](#getnextunblocknotification)|Возвращает следующий `IUMSUnblockNotification` интерфейс в цепочке, возвращенный методом `IUMSCompletionList::GetUnblockNotifications`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IUMSUnblockNotification`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="getcontext"></a>Метод IUMSUnblockNotification::GetContext  
 Возвращает `IExecutionContext` интерфейс для контекста выполнения, связанного с прокси-поток, который был разблокирован. Когда этот метод возвращает базовый контекст выполнения поставлена через вызов `IThreadProxy::SwitchTo` метод, этот интерфейс больше не является допустимым.  
  
```
virtual IExecutionContext* GetContext() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `IExecutionContext` Интерфейс для контекста выполнения на прокси-поток, который был разблокирован.  
  
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
