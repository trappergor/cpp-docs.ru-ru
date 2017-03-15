---
title: "Класс bad_target | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::bad_target
dev_langs:
- C++
helpviewer_keywords:
- bad_target class
ms.assetid: e6dcddbf-9217-4fac-ac7f-7b8b4781d2f5
caps.latest.revision: 19
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
ms.openlocfilehash: a22ebb69195dcea91799dc1c2e301a578dd227bc
ms.lasthandoff: 02/24/2017

---
# <a name="badtarget-class"></a>Класс bad_target
Этот класс описывает исключение, которое создается, если блок обмена сообщениями получает указатель на целевой объект, который неверен для выполняемой операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class bad_target : public std::exception;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор bad_target](#ctor)|Перегружен. Создает объект `bad_target`.|  
  
## <a name="remarks"></a>Примечания  
 Это исключение обычно вызывается по причинам, как целевой объект попытается потреблять сообщения, которое зарезервировано для другой целевой объект или освобождение резервирование, которое не содержит.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `bad_target`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="a-namectora-badtarget"></a><a name="ctor"></a>bad_target 

 Создает объект `bad_target`.  
  
```
explicit _CRTIMP bad_target(_In_z_ const char* _Message) throw();

bad_target() throw();
```  
  
### <a name="parameters"></a>Параметры  
 `_Message`  
 Описательное сообщение об ошибке.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md)




