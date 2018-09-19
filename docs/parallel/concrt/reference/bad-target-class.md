---
title: Класс bad_target | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- bad_target
- CONCRT/concurrency::bad_target
- CONCRT/concurrency::bad_target::bad_target
dev_langs:
- C++
helpviewer_keywords:
- bad_target class
ms.assetid: e6dcddbf-9217-4fac-ac7f-7b8b4781d2f5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 12e035a27693fcad095cd83880aba99c37ba1c1f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027639"
---
# <a name="badtarget-class"></a>Класс bad_target
Этот класс описывает исключение, которое создается, если блок обмена сообщениями получает указатель на целевой объект, который неверен для выполняемой операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class bad_target : public std::exception;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[bad_target](#ctor)|Перегружен. Создает объект `bad_target`.|  
  
## <a name="remarks"></a>Примечания  
 Это исключение обычно вызывается по причинам, например попытка получить сообщение, которое зарезервировано для другой целевой объект или освобождение резервирование, которое не содержит целевого объекта.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `bad_target`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="ctor"></a> bad_target 

 Создает объект `bad_target`.  
  
```
explicit _CRTIMP bad_target(_In_z_ const char* _Message) throw();

bad_target() throw();
```  
  
### <a name="parameters"></a>Параметры  
*_Message*<br/>
Описательное сообщение об ошибке.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md)



