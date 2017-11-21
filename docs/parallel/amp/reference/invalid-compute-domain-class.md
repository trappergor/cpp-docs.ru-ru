---
title: "Класс invalid_compute_domain | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- invalid_compute_domain
- AMPRT/invalid_compute_domain
- AMPRT/Concurrency::invalid_compute_domain::invalid_compute_domain
dev_langs: C++
helpviewer_keywords: invalid_compute_domain class
ms.assetid: ac7a7166-8bdb-4db1-8caf-ea129ab5117e
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a6b41017563a7bd3c6e5ebfd3fc3752ea1e97c3a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="invalidcomputedomain-class"></a>invalid_compute_domain - класс
Исключение, возникающее, когда среда выполнения не может запустить ядро, используя указанные в домене вычислений [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each) место вызова.  

  
## <a name="syntax"></a>Синтаксис  
  
```  
class invalid_compute_domain : public runtime_exception;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[invalid_compute_domain конструктор](#ctor)|Инициализирует новый экземпляр класса `invalid_compute_domain`.|  

  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `runtime_exception`  
  
 `invalid_compute_domain`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amprt.h  
  
 **Пространство имен** : Concurrency  

## <a name="ctor"></a>invalid_compute_domain 

Инициализирует новый экземпляр класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
explicit invalid_compute_domain(  
    const char * _Message ) throw();  
  
invalid_compute_domain() throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `_Message`  
 Описание ошибки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Экземпляр `invalid_compute_domain` класса  
    
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
