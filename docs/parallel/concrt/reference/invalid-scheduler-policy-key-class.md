---
title: "Класс invalid_scheduler_policy_key | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- invalid_scheduler_policy_key
- CONCRT/concurrency::invalid_scheduler_policy_key
- CONCRT/concurrency::invalid_scheduler_policy_key::invalid_scheduler_policy_key
dev_langs: C++
helpviewer_keywords: invalid_scheduler_policy_key class
ms.assetid: 6a7c42fe-9bc4-4a02-bebb-99fe9ef9817d
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 8de8f3a9a027a1b9ae4862d21e27a45f110047b4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="invalidschedulerpolicykey-class"></a>Класс invalid_scheduler_policy_key
Этот класс описывает исключение, создаваемое, когда конструктору объекта `SchedulerPolicy` передается неверный или неизвестный ключ или методу `SetPolicyValue` объекта `SchedulerPolicy` передается ключ, который должен быть изменен другими средствами, такими как метод `SetConcurrencyLimits`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class invalid_scheduler_policy_key : public std::exception;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[invalid_scheduler_policy_key](#ctor)|Перегружен. Создает объект `invalid_scheduler_policy_key`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `invalid_scheduler_policy_key`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="ctor"></a>invalid_scheduler_policy_key 

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
