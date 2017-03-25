---
title: "Класс task_canceled | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- task_canceled
- CONCRT/concurrency::task_canceled
- CONCRT/concurrency::task_canceled::task_canceled
dev_langs:
- C++
helpviewer_keywords:
- task_canceled class
ms.assetid: c3f0b234-2cc1-435f-a48e-995f45b190be
caps.latest.revision: 11
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
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 8f84564a96557c14eb9491b9d1a1d369326751fd
ms.lasthandoff: 03/17/2017

---
# <a name="taskcanceled-class"></a>Класс task_canceled
Этот класс описывает исключение, которое создается уровнем задач PPL для принудительной отмены текущей задачи. Оно также создается методом `get()` метод [задачи](/visualstudio/extensibility/debugger/task-class-internal-members), для отмененной задачи.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class task_canceled : public std::exception;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[task_canceled](#ctor)|Перегружен. Создает объект `task_canceled`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `task_canceled`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="ctor"></a>task_canceled 

 Создает объект `task_canceled`.  
  
```
explicit _CRTIMP task_canceled(_In_z_ const char* _Message) throw();

task_canceled() throw();
```  
  
### <a name="parameters"></a>Параметры  
 `_Message`  
 Описательное сообщение об ошибке.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)

