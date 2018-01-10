---
title: "Класс improper_scheduler_detach | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- improper_scheduler_detach
- CONCRT/concurrency::improper_scheduler_detach
- CONCRT/concurrency::improper_scheduler_detach::improper_scheduler_detach
dev_langs: C++
helpviewer_keywords: improper_scheduler_detach class
ms.assetid: 30132102-c900-4951-a470-b63b4e3aa2d2
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 787d038c65eb6bec2813e30e9bef412205565190
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="improperschedulerdetach-class"></a>Класс improper_scheduler_detach
Этот класс описывает исключение, создаваемое при вызове метода `CurrentScheduler::Detach` в контексте, который не присоединен ни к одному планировщику с помощью метода `Attach` объекта `Scheduler`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class improper_scheduler_detach : public std::exception;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[improper_scheduler_detach](#ctor)|Перегружен. Создает объект `improper_scheduler_detach`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `improper_scheduler_detach`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="ctor"></a>improper_scheduler_detach 

 Создает объект `improper_scheduler_detach`.  
  
```
explicit _CRTIMP improper_scheduler_detach(_In_z_ const char* _Message) throw();

improper_scheduler_detach() throw();
```  
  
### <a name="parameters"></a>Параметры  
 `_Message`  
 Описательное сообщение об ошибке.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс Scheduler](scheduler-class.md)
