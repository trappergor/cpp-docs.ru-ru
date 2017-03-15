---
title: "Структура IUMSCompletionList | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrtrm/concurrency::IUMSCompletionList
dev_langs:
- C++
helpviewer_keywords:
- IUMSCompletionList structure
ms.assetid: 81b5250e-3065-492c-b20d-2cdabf12271a
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
translationtype: Machine Translation
ms.sourcegitcommit: fa774c7f025b581d65c28d65d83e22ff2d798230
ms.openlocfilehash: 25023c27244669092e0f57fe59bdb190fd2f2afb
ms.lasthandoff: 02/24/2017

---
# <a name="iumscompletionlist-structure"></a>Структура IUMSCompletionList
Представляет список выполнения UMS. Когда поток UMS блокируется, отправляется назначенный планировщиком контекст планирования для принятия решения о том, что нужно запланировать для корня базового виртуального процессора, пока исходный поток заблокирован. Когда снимается блокировка исходного потока, операционная система ставит его в очередь списка выполнения, который доступен через этот интерфейс. Планировщик может запросить список выполнения в назначенном контексте планирования или в другом месте, в котором он выполняет поиск работы.  
  
## <a name="syntax"></a>Синтаксис  
  
```
struct IUMSCompletionList;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод IUMSCompletionList::GetUnblockNotifications](#getunblocknotifications)|Получает цепь `IUMSUnblockNotification` интерфейсов, представляющих контексты выполнения, чьи связанные потоки прокси разблокированы со времени последнего этот метод был вызван.|  
  
## <a name="remarks"></a>Примечания  
 Планировщик должен быть чрезвычайно осторожным, какие действия выполняются после использования этого интерфейса для извлечения из очереди элементов из списка завершения. Элементы должны размещаться на список работоспособных контекстов планировщика и быть общедоступными как можно быстрее. Это вполне возможно, что один из элементов, выведенного из очереди получил владение произвольной блокировки. Планировщик не может выполнять произвольные вызовы функции, которые могут блокировать между вызовом для извлечения элементов из очереди и размещение этих элементов в список, который может быть обычно доступен из планировщика.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IUMSCompletionList`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrtrm.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namegetunblocknotificationsa--iumscompletionlistgetunblocknotifications-method"></a><a name="getunblocknotifications"></a>Метод IUMSCompletionList::GetUnblockNotifications  
 Получает цепь `IUMSUnblockNotification` интерфейсов, представляющих контексты выполнения, чьи связанные потоки прокси разблокированы со времени последнего этот метод был вызван.  
  
```
virtual IUMSUnblockNotification *GetUnblockNotifications() = 0;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Цепочка `IUMSUnblockNotification` интерфейсов.  
  
### <a name="remarks"></a>Примечания  
 После перепланирования контекстов выполнения, возвращенные уведомления являются недопустимыми.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Структура IUMSScheduler](iumsscheduler-structure.md)   
 [Структура IUMSUnblockNotification](iumsunblocknotification-structure.md)

