---
title: "Класс scheduler_not_attached | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::scheduler_not_attached
dev_langs:
- C++
helpviewer_keywords:
- scheduler_not_attached class
ms.assetid: 26001970-b400-463b-be3d-8623359c399a
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
ms.openlocfilehash: 4ee1cbe219b7a1fc5a646afd5e975e84be949f65
ms.lasthandoff: 02/24/2017

---
# <a name="schedulernotattached-class"></a>Класс scheduler_not_attached
Этот класс описывает исключение, создаваемое при выполнении операции, при которой планировщик должен был присоединен к текущему контексту, а он не присоединен.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class scheduler_not_attached : public std::exception;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор scheduler_not_attached](#ctor)|Перегружен. Создает объект `scheduler_not_attached`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `scheduler_not_attached`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namectora-schedulernotattached"></a><a name="ctor"></a>scheduler_not_attached 

 Создает объект `scheduler_not_attached`.  
  
```
explicit _CRTIMP scheduler_not_attached(_In_z_ const char* _Message) throw();

scheduler_not_attached() throw();
```  
  
### <a name="parameters"></a>Параметры  
 `_Message`  
 Описательное сообщение об ошибке.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс планировщика](scheduler-class.md)

