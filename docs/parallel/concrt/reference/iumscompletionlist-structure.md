---
title: "Структура IUMSCompletionList | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList
- CONCRTRM/concurrency::IUMSCompletionList::IUMSCompletionList::GetUnblockNotifications
dev_langs:
- C++
helpviewer_keywords:
- IUMSCompletionList structure
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 378eccbc0e29a9356ffd89699039b9877c76c751
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="iumscompletionlist-structure"></a>Структура IUMSCompletionList
Представляет список выполнения UMS. Когда поток UMS блокируется, отправляется назначенный планировщиком контекст планирования для принятия решения о том, что нужно запланировать для корня базового виртуального процессора, пока исходный поток заблокирован. Когда снимается блокировка исходного потока, операционная система ставит его в очередь списка выполнения, который доступен через этот интерфейс. Планировщик может запросить список выполнения в назначенном контексте планирования или в другом месте, в котором он выполняет поиск работы.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct IUMSCompletionList;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[IUMSCompletionList::GetUnblockNotifications](#getunblocknotifications)|Извлекает цепочки `IUMSUnblockNotification` интерфейсов, представляющих контексты выполнения, чьи связанные потоки прокси разблокированы со времени последнего этот метод был вызван.|  
  
## <a name="remarks"></a>Примечания  
 Планировщик должен быть чрезвычайно осторожным, какие действия должны выполняться после использования этого интерфейса для извлечения элементов из списка завершения очереди. Элементы должны размещаться на список работоспособных контекстов планировщика и быть общедоступными как можно быстрее. Это вполне возможно, что один из элементов, выведенного из очереди получил владение произвольной блокировки. Планировщик не может выполнять произвольные вызовы функции, которые могут блокировать между для извлечения элементов из очереди и размещение этих элементов в список, который можно будет обычно доступен в планировщике.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IUMSCompletionList`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="getunblocknotifications"></a>  Метод IUMSCompletionList::GetUnblockNotifications  
 Извлекает цепочки `IUMSUnblockNotification` интерфейсов, представляющих контексты выполнения, чьи связанные потоки прокси разблокированы со времени последнего этот метод был вызван.  
  
```
virtual IUMSUnblockNotification *GetUnblockNotifications() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Цепочка `IUMSUnblockNotification` интерфейсов.  
  
### <a name="remarks"></a>Примечания  
 После были заново запланированы контекстов выполнения, возвращенные уведомления являются недопустимыми.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Структура IUMSScheduler](iumsscheduler-structure.md)   
 [Структура IUMSUnblockNotification](iumsunblocknotification-structure.md)
