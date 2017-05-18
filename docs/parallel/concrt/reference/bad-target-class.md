---
title: "Класс bad_target | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- bad_target
- CONCRT/concurrency::bad_target
- CONCRT/concurrency::bad_target::bad_target
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: 145aa17b4589fb572f3b6594360ec69db5e15287
ms.contentlocale: ru-ru
ms.lasthandoff: 03/17/2017

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
|[bad_target](#ctor)|Перегружен. Создает объект `bad_target`.|  
  
## <a name="remarks"></a>Примечания  
 Это исключение обычно вызывается по причинам, как целевой объект попытается потреблять сообщения, которое зарезервировано для другой целевой объект или освобождение резервирование, которое не содержит.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `bad_target`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="ctor"></a>bad_target 

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




