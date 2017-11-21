---
title: "Класс improper_lock | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- improper_lock
- CONCRT/concurrency::improper_lock
- CONCRT/concurrency::improper_lock::improper_lock
dev_langs: C++
helpviewer_keywords: improper_lock class
ms.assetid: 8f494942-7748-4a2a-8de2-23414bfe6346
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 2da7827afe8bed49c514eda10ce16c16b434c9f8
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="improperlock-class"></a>Класс improper_lock
Этот класс описывает исключение, создаваемое, когда блокировка получена неправильно.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class improper_lock : public std::exception;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[improper_lock](#ctor)|Перегружен. Создает элемент `improper_lock exception`.|  
  
## <a name="remarks"></a>Примечания  
 Как правило это исключение вызывается при попытке получить блокировку допускает повторные входы рекурсивно на том же контексте.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `improper_lock`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="ctor"></a>improper_lock 

 Создает элемент `improper_lock exception`.  
  
```
explicit _CRTIMP improper_lock(_In_z_ const char* _Message) throw();

improper_lock() throw();
```  
  
### <a name="parameters"></a>Параметры  
 `_Message`  
 Описательное сообщение об ошибке.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс critical_section](critical-section-class.md)   
 [Класс reader_writer_lock](reader-writer-lock-class.md)
