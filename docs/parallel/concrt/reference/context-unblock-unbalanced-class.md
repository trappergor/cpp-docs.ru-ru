---
title: "Класс context_unblock_unbalanced | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced::context_unblock_unbalanced
dev_langs:
- C++
helpviewer_keywords:
- context_unblock_unbalanced class
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 21c26658e347fa35209677e15ddcb48bbe8d1235
ms.contentlocale: ru-ru
ms.lasthandoff: 03/17/2017

---
# <a name="contextunblockunbalanced-class"></a>Класс context_unblock_unbalanced
Данный класс описывает исключение, создаваемое, если вызовы методов `Block` и `Unblock` объекта `Context` объединены неправильно.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class context_unblock_unbalanced : public std::exception;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[context_unblock_unbalanced](#ctor)|Перегружен. Создает объект `context_unblock_unbalanced`.|  
  
## <a name="remarks"></a>Примечания  
 Вызовы `Block` и `Unblock` методы `Context` объект должен всегда быть правильно пару. Среда выполнения с параллелизмом позволяет операциям происходить в любом порядке. Например, за вызовом `Block` может следовать вызов `Unblock`, или наоборот. Это исключение будет вызываться, если, например, два вызова к `Unblock` метод были внесены в строке, на `Context` объект, который не был заблокирован.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `context_unblock_unbalanced`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="ctor"></a>context_unblock_unbalanced 

 Создает объект `context_unblock_unbalanced`.  
  
```  
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

 
context_unblock_unbalanced() throw();
```  
  
### <a name="parameters"></a>Параметры  
 `_Message`  
 Описательное сообщение об ошибке.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)

