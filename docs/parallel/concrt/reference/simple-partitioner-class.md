---
title: "Класс simple_partitioner | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ppl/concurrency::simple_partitioner
dev_langs:
- C++
helpviewer_keywords:
- simple_partitioner class
ms.assetid: d7e997af-54d1-43f5-abe0-def72df6edb3
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
ms.openlocfilehash: dc90df5ba9fbbf5566a26a014a6a2db2ae4a0459
ms.lasthandoff: 02/24/2017

---
# <a name="simplepartitioner-class"></a>Класс simple_partitioner
Класс `simple_partitioner` представляет статическое разделение диапазона, в котором итерации выполняются с помощью `parallel_for`. Разделитель делит диапазон на фрагменты таким образом, что каждый фрагмент имеет число итераций не менее указанного размера фрагмента.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class simple_partitioner;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор simple_partitioner](#ctor)|Создает объект `simple_partitioner`.|  
|[~ simple_partitioner деструктор](#dtor)|Уничтожает объект `simple_partitioner`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `simple_partitioner`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ppl.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namedtora-simplepartitioner"></a><a name="dtor"></a>~ simple_partitioner 

 Уничтожает объект `simple_partitioner`.  
  
```
~simple_partitioner();
```  
  
##  <a name="a-namectora-simplepartitioner"></a><a name="ctor"></a>simple_partitioner 

 Создает объект `simple_partitioner`.  
  
```
explicit simple_partitioner(_Size_type _Chunk_size);
```  
  
### <a name="parameters"></a>Параметры  
 `_Chunk_size`  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)

