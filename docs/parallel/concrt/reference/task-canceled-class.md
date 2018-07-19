---
title: Класс task_canceled | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- task_canceled
- CONCRT/concurrency::task_canceled
- CONCRT/concurrency::task_canceled::task_canceled
dev_langs:
- C++
helpviewer_keywords:
- task_canceled class
ms.assetid: c3f0b234-2cc1-435f-a48e-995f45b190be
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 1f535a4cce75d388437025967b9c0c9b1ae0fd7a
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33690251"
---
# <a name="taskcanceled-class"></a>Класс task_canceled
Этот класс описывает исключение, которое создается уровнем задач PPL для принудительной отмены текущей задачи. Оно также создается методом `get()` метод [задачи](/visualstudio/extensibility/debugger/task-class-internal-members), для отмененной задачи.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class task_canceled : public std::exception;
```  
  
## <a name="members"></a>Участники  
  
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
  
##  <a name="ctor"></a> task_canceled 

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
