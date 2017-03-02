---
title: "Класс auto_partitioner | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ppl/concurrency::auto_partitioner
dev_langs:
- C++
helpviewer_keywords:
- auto_partitioner class
ms.assetid: 7cc08e5d-20b4-47a4-b4b5-c214a78f5a9e
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
ms.openlocfilehash: 8092a0d6c4fe6053a3bb7e80e659ab6a7628664a
ms.lasthandoff: 02/24/2017

---
# <a name="autopartitioner-class"></a>Класс auto_partitioner
Класс `auto_partitioner` представляет метод, который алгоритмы `parallel_for`, `parallel_for_each` и `parallel_transform` используют по умолчанию для разделения обрабатываемого диапазона. Этот метод разделения использует как перенос диапазона для распределения нагрузки, так и отмену по итерациям.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class auto_partitioner;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор auto_partitioner](#ctor)|Создает объект `auto_partitioner`.|  
|[~ auto_partitioner деструктор](#dtor)|Уничтожает объект `auto_partitioner`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `auto_partitioner`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ppl.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namedtora-autopartitioner"></a><a name="dtor"></a>~ auto_partitioner 

 Уничтожает объект `auto_partitioner`.  
  
```
~auto_partitioner();
```  
  
##  <a name="a-namectora-autopartitioner"></a><a name="ctor"></a>auto_partitioner 

 Создает объект `auto_partitioner`.  
  
```
auto_partitioner();
```  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)

