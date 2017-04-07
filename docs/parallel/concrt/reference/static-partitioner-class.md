---
title: "Класс static_partitioner | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- static_partitioner
- PPL/concurrency::static_partitioner
- PPL/concurrency::static_partitioner::static_partitioner
dev_langs:
- C++
helpviewer_keywords:
- static_partitioner class
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
caps.latest.revision: 8
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
ms.openlocfilehash: 84cdbb30068f8dd9d2a1130e53d06d9b718b0c02
ms.lasthandoff: 03/17/2017

---
# <a name="staticpartitioner-class"></a>Класс static_partitioner
Класс `static_partitioner` представляет статическое разделение диапазона, в котором итерации выполняются с помощью `parallel_for`. Разделитель делит диапазон на количество блоков, соответствующее количеству работников, доступных базовому планировщику.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class static_partitioner;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[static_partitioner](#ctor)|Создает объект `static_partitioner`.|  
|[~ static_partitioner деструктор](#dtor)|Уничтожает объект `static_partitioner`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `static_partitioner`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ppl.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="dtor"></a>~ static_partitioner 

 Уничтожает объект `static_partitioner`.  
  
```
~static_partitioner();
```  
  
##  <a name="ctor"></a>static_partitioner 

 Создает объект `static_partitioner`.  
  
```
static_partitioner();
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)

