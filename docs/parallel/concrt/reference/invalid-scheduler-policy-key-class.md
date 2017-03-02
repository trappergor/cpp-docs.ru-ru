---
title: "Класс invalid_scheduler_policy_key | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_key
dev_langs:
- C++
helpviewer_keywords:
- invalid_scheduler_policy_key class
ms.assetid: 6a7c42fe-9bc4-4a02-bebb-99fe9ef9817d
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: ba23cb216581862ed110cace9b7fff9024df6899
ms.lasthandoff: 02/24/2017

---
# <a name="invalidschedulerpolicykey-class"></a>Класс invalid_scheduler_policy_key
Этот класс описывает исключение, создаваемое, когда конструктору объекта `SchedulerPolicy` передается неверный или неизвестный ключ или методу `SetPolicyValue` объекта `SchedulerPolicy` передается ключ, который должен быть изменен другими средствами, такими как метод `SetConcurrencyLimits`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class invalid_scheduler_policy_key : public std::exception;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор invalid_scheduler_policy_key](#ctor)|Перегружен. Создает объект `invalid_scheduler_policy_key`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `invalid_scheduler_policy_key`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namectora-invalidschedulerpolicykey"></a><a name="ctor"></a>invalid_scheduler_policy_key 

 Создает объект `invalid_scheduler_policy_key`.  
  
```
explicit _CRTIMP invalid_scheduler_policy_key(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_key() throw();
```  
  
### <a name="parameters"></a>Параметры  
 `_Message`  
 Описательное сообщение об ошибке.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс SchedulerPolicy](schedulerpolicy-class.md)

