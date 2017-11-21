---
title: "Класс nested_scheduler_missing_detach | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach
- CONCRT/concurrency::nested_scheduler_missing_detach::nested_scheduler_missing_detach
dev_langs: C++
helpviewer_keywords: nested_scheduler_missing_detach class
ms.assetid: 65d3f277-6d43-4160-97ef-caf8b26c1641
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 78939c1146ec00bf2c4723b17caa294ea00c2f84
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="nestedschedulermissingdetach-class"></a>Класс nested_scheduler_missing_detach
Этот класс описывает исключение, которое возникает, когда исполняющая среда с параллелизмом обнаруживает, что вы не вызвали метод `CurrentScheduler::Detach` для контекста, который присоединился ко второму планировщику с помощью метода `Attach` объекта `Scheduler`.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class nested_scheduler_missing_detach : public std::exception;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[nested_scheduler_missing_detach](#ctor)|Перегружен. Создает объект `nested_scheduler_missing_detach`.|  
  
## <a name="remarks"></a>Примечания  
 Это исключение возникает, только когда один планировщик вложен внутрь другого путем вызова метода `Attach` объекта `Scheduler` для контекста, которым уже владеет другой планировщик или к которому он уже прикреплен. Среда выполнения с параллелизмом возможности создает исключение, если она может обнаружить сценарий как вспомогательное средство Поиск неполадки. Не каждый экземпляр игнорирования для вызова `CurrentScheduler::Detach` метод гарантированно это исключение.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `nested_scheduler_missing_detach`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="ctor"></a>nested_scheduler_missing_detach 

 Создает объект `nested_scheduler_missing_detach`.  
  
```
explicit _CRTIMP nested_scheduler_missing_detach(_In_z_ const char* _Message) throw();

nested_scheduler_missing_detach() throw();
```  
  
### <a name="parameters"></a>Параметры  
 `_Message`  
 Описательное сообщение об ошибке.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс Scheduler](scheduler-class.md)
