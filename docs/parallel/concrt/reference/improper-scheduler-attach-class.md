---
title: "Класс improper_scheduler_attach | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- improper_scheduler_attach
- CONCRT/concurrency::improper_scheduler_attach
- CONCRT/concurrency::improper_scheduler_attach::improper_scheduler_attach
dev_langs: C++
helpviewer_keywords: improper_scheduler_attach class
ms.assetid: 5a76da0a-091b-4748-8f62-b3a28f674f9e
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 6735c8a4ea69b56ead58d3fc7cb29fd0b2208d8e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="improperschedulerattach-class"></a>Класс improper_scheduler_attach
Этот класс описывает исключение, которое создается при вызове метода `Attach` на объекте `Scheduler`, который уже присоединен к текущему контексту.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class improper_scheduler_attach : public std::exception;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[improper_scheduler_attach](#ctor)|Перегружен. Создает объект `improper_scheduler_attach`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `improper_scheduler_attach`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="ctor"></a>improper_scheduler_attach 

 Создает объект `improper_scheduler_attach`.  
  
```
explicit _CRTIMP improper_scheduler_attach(_In_z_ const char* _Message) throw();

improper_scheduler_attach() throw();
```  
  
### <a name="parameters"></a>Параметры  
 `_Message`  
 Описательное сообщение об ошибке.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Класс Scheduler](scheduler-class.md)
