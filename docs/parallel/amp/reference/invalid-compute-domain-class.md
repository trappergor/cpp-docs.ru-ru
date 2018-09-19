---
title: Класс invalid_compute_domain | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- invalid_compute_domain
- AMPRT/invalid_compute_domain
- AMPRT/Concurrency::invalid_compute_domain::invalid_compute_domain
dev_langs:
- C++
helpviewer_keywords:
- invalid_compute_domain class
ms.assetid: ac7a7166-8bdb-4db1-8caf-ea129ab5117e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: def102ecb8063f82d90d41b2b678ff22638b1f8b
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46116013"
---
# <a name="invalidcomputedomain-class"></a>invalid_compute_domain - класс
Исключение, возникающее, когда среда выполнения не может запустить ядро с помощью вычислительного домена, указанного в [parallel_for_each](concurrency-namespace-functions-amp.md#parallel_for_each) место вызова.  

  
## <a name="syntax"></a>Синтаксис  
  
```  
class invalid_compute_domain : public runtime_exception;  
```  
  
## <a name="members"></a>Участники  
  
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

## <a name="ctor"></a> invalid_compute_domain 

Инициализирует новый экземпляр класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
explicit invalid_compute_domain(  
    const char * _Message ) throw();  
  
invalid_compute_domain() throw();  
```  
  
### <a name="parameters"></a>Параметры  
*_Message*<br/>
Описание ошибки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Экземпляр `invalid_compute_domain` класса  
    
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
