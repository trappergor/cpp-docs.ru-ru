---
title: "Класс invalid_scheduler_policy_thread_specification | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_thread_specification
dev_langs:
- C++
helpviewer_keywords:
- invalid_scheduler_policy_thread_specification class
ms.assetid: 2d0fafb2-18f8-4284-8040-3db640d33303
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
ms.openlocfilehash: c09719412e38a4f056eabc39a66a684caa0659d4
ms.lasthandoff: 02/24/2017

---
# <a name="invalidschedulerpolicythreadspecification-class"></a>Класс invalid_scheduler_policy_thread_specification
Данный класс описывает исключение, создаваемое при попытке установить ограничения параллельности объекта `SchedulerPolicy` таким образом, чтобы значение ключа `MinConcurrency` было меньше, чем значение ключа `MaxConcurrency`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class invalid_scheduler_policy_thread_specification : public std::exception;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[invalid_scheduler_policy_thread_specification конструктор] (недопустимый планировщика политики — значение class.md #ctor|Перегружен. Создает объект `invalid_scheduler_policy_value`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `invalid_scheduler_policy_thread_specification`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
##  <a name="a-namectora-invalidschedulerpolicythreadspecification"></a><a name="ctor"></a>invalid_scheduler_policy_thread_specification 

 Создает объект `invalid_scheduler_policy_value`.  
  
```
explicit _CRTIMP invalid_scheduler_policy_thread_specification(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_thread_specification() throw();
```  
  
### <a name="parameters"></a>Параметры  
 `_Message`  
 Описательное сообщение об ошибке.  

## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс SchedulerPolicy](schedulerpolicy-class.md)

