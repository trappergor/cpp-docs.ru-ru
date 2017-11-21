---
title: "Класс invalid_scheduler_policy_value | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: concrt/concurrency::invalid_scheduler_policy_value
dev_langs: C++
helpviewer_keywords: invalid_scheduler_policy_value class
ms.assetid: 8c533e3f-2774-4192-8616-b2313b859bf7
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: dc8d6a06d578169cb60bc757c1719b7028e12b06
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
|[invalid_scheduler_policy_value] (invalid-scheduler-policy-thread-specification-class.md#ctor|Перегружен. Создает объект `invalid_scheduler_policy_value`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `invalid_scheduler_policy_value`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
    
##  <a name="ctor"></a>invalid_scheduler_policy_value 

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
