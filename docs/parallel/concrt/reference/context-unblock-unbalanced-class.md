---
title: Класс context_unblock_unbalanced | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced
- CONCRT/concurrency::context_unblock_unbalanced::context_unblock_unbalanced
dev_langs:
- C++
helpviewer_keywords:
- context_unblock_unbalanced class
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 54911e3e9c696cd2a390dc2f5b42e3917b08014f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46037480"
---
# <a name="contextunblockunbalanced-class"></a>Класс context_unblock_unbalanced
Данный класс описывает исключение, создаваемое, если вызовы методов `Block` и `Unblock` объекта `Context` объединены неправильно.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class context_unblock_unbalanced : public std::exception;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[context_unblock_unbalanced](#ctor)|Перегружен. Создает объект `context_unblock_unbalanced`.|  
  
## <a name="remarks"></a>Примечания  
 Вызовы `Block` и `Unblock` методы `Context` объект должен всегда быть правильно пару. Среда выполнения с параллелизмом позволяет операциям происходить в любом порядке. Например, за вызовом `Block` может следовать вызов `Unblock`, или наоборот. Это исключение выдается, если, например, два вызова к `Unblock` метод были сделаны в строке, на `Context` объект, который не был заблокирован.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `context_unblock_unbalanced`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="ctor"></a> context_unblock_unbalanced 

 Создает объект `context_unblock_unbalanced`.  
  
```  
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

 
context_unblock_unbalanced() throw();
```  
  
### <a name="parameters"></a>Параметры  
*_Message*<br/>
Описательное сообщение об ошибке.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)
