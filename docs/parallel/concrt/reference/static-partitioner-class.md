---
title: Класс static_partitioner | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- static_partitioner
- PPL/concurrency::static_partitioner
- PPL/concurrency::static_partitioner::static_partitioner
dev_langs:
- C++
helpviewer_keywords:
- static_partitioner class
ms.assetid: 2b3dbdf0-6eb9-49f6-8639-03df1d974143
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a15310be9a879a2dbcb117a987e56571e953f825
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33686026"
---
# <a name="staticpartitioner-class"></a>Класс static_partitioner
Класс `static_partitioner` представляет статическое разделение диапазона, в котором итерации выполняются с помощью `parallel_for`. Разделитель делит диапазон на количество блоков, соответствующее количеству работников, доступных базовому планировщику.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class static_partitioner;
```  
  
## <a name="members"></a>Участники  
  
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
  
##  <a name="dtor"></a> ~ static_partitioner 

 Уничтожает объект `static_partitioner`.  
  
```
~static_partitioner();
```  
  
##  <a name="ctor"></a> static_partitioner 

 Создает объект `static_partitioner`.  
  
```
static_partitioner();
```  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)
