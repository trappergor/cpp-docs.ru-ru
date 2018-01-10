---
title: "Класс missing_wait | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- missing_wait
- CONCRT/concurrency::missing_wait
- CONCRT/concurrency::missing_wait::missing_wait
dev_langs: C++
helpviewer_keywords: missing_wait class
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 952a2b88ebb91449341085a923e06d389aa10fe4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="missingwait-class"></a>Класс missing_wait
Этот класс описывает исключение, возникающее при наличии задач, для которых по-прежнему запланирован объект `task_group` или `structured_task_group` на момент выполнения деструктора объекта. Это исключение не создается, если деструктор достигается из-за освобождения стека в результате исключения.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class missing_wait : public std::exception;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[missing_wait](#ctor)|Перегружен. Создает объект `missing_wait`.|  
  
## <a name="remarks"></a>Примечания  
 Отсутствует поток исключение, вы несете ответственность за вызов любого `wait` или `run_and_wait` метод `task_group` или `structured_task_group` объект, прежде чем разрешить этот объект для уничтожения. Среда выполнения создает исключение как признак того, вы забыли вызвать `wait` или `run_and_wait` метод.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `missing_wait`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="ctor"></a>missing_wait 

 Создает объект `missing_wait`.  
  
```
explicit _CRTIMP missing_wait(_In_z_ const char* _Message) throw();

missing_wait() throw();
```  
  
### <a name="parameters"></a>Параметры  
 `_Message`  
 Описательное сообщение об ошибке.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс task_group](task-group-class.md)   
 [Ожидание](task-group-class.md)   
 [run_and_wait](task-group-class.md)   
 [Класс structured_task_group](structured-task-group-class.md)
