---
title: "Класс invalid_scheduler_policy_value | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::invalid_scheduler_policy_value
dev_langs:
- C++
helpviewer_keywords:
- invalid_scheduler_policy_value class
ms.assetid: 8c533e3f-2774-4192-8616-b2313b859bf7
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
ms.openlocfilehash: ff5b07b62923a289da1b47de08b527da212e4a2d
ms.lasthandoff: 02/24/2017

---
# <a name="invalidschedulerpolicyvalue-class"></a>Класс invalid_scheduler_policy_value
Этот класс описывает исключение, создаваемое, когда ключу политики объекта `SchedulerPolicy` присваивается недопустимое для этого ключа значение.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class invalid_scheduler_policy_value : public std::exception;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[invalid_scheduler_policy_value конструктор] (invalid-scheduler-policy-thread-specification-class.md#ctor|Перегружен. Создает объект `invalid_scheduler_policy_value`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `invalid_scheduler_policy_value`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
    
##  <a name="a-namectora-invalidschedulerpolicyvalue"></a><a name="ctor"></a>invalid_scheduler_policy_value 

 Создает объект `invalid_scheduler_policy_value`.  
  
```
explicit _CRTIMP invalid_scheduler_policy_value(_In_z_ const char* _Message) throw();

invalid_scheduler_policy_value() throw();
```  
  
### <a name="parameters"></a>Параметры  
 `_Message`  
 Описательное сообщение об ошибке.  
  

## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс SchedulerPolicy](schedulerpolicy-class.md)

