---
title: "Класс invalid_operation | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::invalid_operation
dev_langs:
- C++
helpviewer_keywords:
- invalid_operation class
ms.assetid: 26ba07dc-fcdf-44cb-b748-a31d35205b52
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
ms.openlocfilehash: 0484e149409b2515f60b2e9aa34a85d5381e05a5
ms.lasthandoff: 02/24/2017

---
# <a name="invalidoperation-class"></a>Класс invalid_operation
Данный класс описывает исключение, возникающее при выполнении недопустимой операции, которая не описывается более точно другим типом исключения, создаваемым средой выполнения с параллелизмом.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class invalid_operation : public std::exception;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор invalid_operation](#ctor)|Перегружен. Создает объект `invalid_operation`.|  
  
## <a name="remarks"></a>Примечания  
 Различные методы, создающие это исключение, обычно документируют, в каких обстоятельствах они создают его.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `invalid_operation`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namectora-invalidoperation"></a><a name="ctor"></a>invalid_operation 

 Создает объект `invalid_operation`.  
  
```
explicit _CRTIMP invalid_operation(_In_z_ const char* _Message) throw();

invalid_operation() throw();
```  
  
### <a name="parameters"></a>Параметры  
 `_Message`  
 Описательное сообщение об ошибке.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)

