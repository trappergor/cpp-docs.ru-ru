---
title: "Класс affinity_partitioner | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- affinity_partitioner
- PPL/concurrency::affinity_partitioner
- PPL/concurrency::affinity_partitioner::affinity_partitioner
dev_langs: C++
helpviewer_keywords: affinity_partitioner class
ms.assetid: 31bf7bb1-bd01-491c-9760-d9d60edfccad
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3f1ed1b9fee094669a2c1d0ce7c7e51f6d8d5fcd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
|[affinity_partitioner](#ctor)|Создает объект `affinity_partitioner`.|  
|[~ affinity_partitioner деструктор](#dtor)|Уничтожает `affinity_partitioner` объекта.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `affinity_partitioner`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ppl.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="dtor"></a>~ affinity_partitioner 

 Уничтожает `affinity_partitioner` объекта.  
  
```
~affinity_partitioner();
```  
  
##  <a name="ctor"></a>affinity_partitioner 

 Создает объект `affinity_partitioner`.  
  
```
affinity_partitioner();
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)
