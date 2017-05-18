---
title: "Класс auto_partitioner | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- auto_partitioner
- PPL/concurrency::auto_partitioner
- PPL/concurrency::auto_partitioner::auto_partitioner
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: d5404f934a219649f1e8e53c1ff156a34a901f58
ms.contentlocale: ru-ru
ms.lasthandoff: 03/17/2017

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
|[auto_partitioner](#ctor)|Создает объект `auto_partitioner`.|  
|[~ auto_partitioner деструктор](#dtor)|Уничтожает объект `auto_partitioner`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `auto_partitioner`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** ppl.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="dtor"></a>~ auto_partitioner 

 Уничтожает объект `auto_partitioner`.  
  
```
~auto_partitioner();
```  
  
##  <a name="ctor"></a>auto_partitioner 

 Создает объект `auto_partitioner`.  
  
```
auto_partitioner();
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)

