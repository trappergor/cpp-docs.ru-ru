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
- ppl/concurrency::static_partitioner
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: f36b1e1dcc68d94bdebd8b7b10f4fec735ce9fb5
ms.lasthandoff: 02/24/2017

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
|[Конструктор static_partitioner](#ctor)|Создает объект `static_partitioner`.|  
|[~ static_partitioner деструктор](#dtor)|Уничтожает объект `static_partitioner`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `static_partitioner`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ppl.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namedtora-staticpartitioner"></a><a name="dtor"></a>~ static_partitioner 

 Уничтожает объект `static_partitioner`.  
  
```
~static_partitioner();
```  
  
##  <a name="a-namectora-staticpartitioner"></a><a name="ctor"></a>static_partitioner 

 Создает объект `static_partitioner`.  
  
```
static_partitioner();
```  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)

