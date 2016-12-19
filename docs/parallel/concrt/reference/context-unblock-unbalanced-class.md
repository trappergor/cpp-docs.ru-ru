---
title: "Класс context_unblock_unbalanced | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "concrt/concurrency::context_unblock_unbalanced"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "context_unblock_unbalanced - класс"
ms.assetid: a76066c8-19dd-44fa-959a-6941ec1b0d2d
caps.latest.revision: 20
caps.handback.revision: 20
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс context_unblock_unbalanced
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Данный класс описывает исключение, создаваемое, если вызовы методов `Block` и `Unblock` объекта `Context` объединены неправильно.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class context_unblock_unbalanced : public std::exception;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор context_unblock_unbalanced::context_unblock_unbalanced](#context_unblock_unbalanced__context_unblock_unbalanced_constructor)|Перегружен. Создает объект `context_unblock_unbalanced`.|  
  
## <a name="remarks"></a>Примечания  
 Вызовы функций `Block` и `Unblock` методы `Context` объект должен всегда быть правильно пару. Среда выполнения с параллелизмом позволяет операциям происходить в любом порядке. Например, за вызовом `Block` может следовать вызов `Unblock`, или наоборот. Это исключение будет вызываться, если, например, два вызова к `Unblock` метод были внесены в строке, на `Context` объект, который не был заблокирован.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `context_unblock_unbalanced`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namecontextunblockunbalancedcontextunblockunbalancedconstructora-contextunblockunbalancedcontextunblockunbalanced-constructor"></a><a name="context_unblock_unbalanced__context_unblock_unbalanced_constructor"></a>  Конструктор context_unblock_unbalanced::context_unblock_unbalanced  
 Создает объект `context_unblock_unbalanced`.  
  
```  
explicit _CRTIMP context_unblock_unbalanced(_In_z_ const char* _Message) throw();

 
context_unblock_unbalanced() throw();
```  
  
### <a name="parameters"></a>Параметры  
 `_Message`  
 Описательное сообщение об ошибке.  
  
## <a name="see-also"></a>См. также раздел  
 [пространство имен Concurrency](../../../parallel/concrt/reference/concurrency-namespace.md)
