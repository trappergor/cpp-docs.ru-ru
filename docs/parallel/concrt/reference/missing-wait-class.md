---
title: "Класс missing_wait | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::missing_wait
dev_langs:
- C++
helpviewer_keywords:
- missing_wait class
ms.assetid: ff981875-bd43-47e3-806f-b03c9f418b18
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
ms.openlocfilehash: 7d29294f4ddce571451a72bf637526e5af283cff
ms.lasthandoff: 02/24/2017

---
# <a name="missingwait-class"></a>Класс missing_wait
Этот класс описывает исключение, возникающее при наличии задач, для которых по-прежнему запланирован объект `task_group` или `structured_task_group` на момент выполнения деструктора объекта. Это исключение не создается, если деструктор достигается из-за освобождения стека в результате исключения.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class missing_wait : public std::exception;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор missing_wait](#ctor)|Перегружен. Создает объект `missing_wait`.|  
  
## <a name="remarks"></a>Примечания  
 Отсутствует поток исключений, вы несете ответственность за вызов либо `wait` или `run_and_wait` метод `task_group` или `structured_task_group` объекта перед разрешением этого объекта для уничтожения. Среда выполнения создает это исключение, как это означает, что вы забыли вызывать `wait` или `run_and_wait` метод.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `missing_wait`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namectora-missingwait"></a><a name="ctor"></a>missing_wait 

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
 [wait-метод](task-group-class.md)   
 [run_and_wait метод](task-group-class.md)   
 [Класс structured_task_group](structured-task-group-class.md)

