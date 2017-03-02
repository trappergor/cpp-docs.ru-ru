---
title: "Класс affinity_partitioner | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ppl/concurrency::affinity_partitioner
dev_langs:
- C++
helpviewer_keywords:
- affinity_partitioner class
ms.assetid: 31bf7bb1-bd01-491c-9760-d9d60edfccad
caps.latest.revision: 9
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
ms.openlocfilehash: 92da56fd5b84537c2fa01a252dfee202c729cc96
ms.lasthandoff: 02/24/2017

---
# <a name="affinitypartitioner-class"></a>Класс affinity_partitioner
Класс `affinity_partitioner` аналогичен классу `static_partitioner`, но он повышает сходство кэша путем подбора поддиапазонов сопоставления для потоков рабочего процесса. Он может значительно повысить производительность, если цикл повторно выполняется в одном и том же наборе данных и данные помещаются в кэш. Обратите внимание, что один и тот же объект `affinity_partitioner` должен использоваться с последующими итерациями параллельного цикла, выполняемого в указанном наборе данных, чтобы воспользоваться преимуществом локальности данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class affinity_partitioner;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор affinity_partitioner](#ctor)|Создает объект `affinity_partitioner`.|  
|[~ affinity_partitioner деструктор](#dtor)|Уничтожает `affinity_partitioner` объекта.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `affinity_partitioner`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ppl.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namedtora-affinitypartitioner"></a><a name="dtor"></a>~ affinity_partitioner 

 Уничтожает `affinity_partitioner` объекта.  
  
```
~affinity_partitioner();
```  
  
##  <a name="a-namectora-affinitypartitioner"></a><a name="ctor"></a>affinity_partitioner 

 Создает объект `affinity_partitioner`.  
  
```
affinity_partitioner();
```  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)

