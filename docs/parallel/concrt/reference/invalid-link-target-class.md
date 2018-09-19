---
title: Класс invalid_link_target | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-concrt
ms.topic: reference
f1_keywords:
- invalid_link_target
- CONCRT/concurrency::invalid_link_target
- CONCRT/concurrency::invalid_link_target::invalid_link_target
dev_langs:
- C++
helpviewer_keywords:
- invalid_link_target class
ms.assetid: 33b64885-34d8-4d4e-a893-02e9f19c958e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2120f274dd783da00a43106338476c43cc0a9dad
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46021750"
---
# <a name="invalidlinktarget-class"></a>Класс invalid_link_target
Данный класс описывает исключение, создаваемое, когда вызывается метод `link_target` блока обмена сообщениями и блок сообщений не может создать связь с целевым объектом. Это может быть результатом превышения числа ссылок, допустимых для блока сообщений, или попытки связать указанную цель с одним и тем же источником дважды.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class invalid_link_target : public std::exception;
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[invalid_link_target](#ctor)|Перегружен. Создает объект `invalid_link_target`.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `invalid_link_target`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="ctor"></a> invalid_link_target 

 Создает объект `invalid_link_target`.  
  
```
explicit _CRTIMP invalid_link_target(_In_z_ const char* _Message) throw();

invalid_link_target() throw();
```  
  
### <a name="parameters"></a>Параметры  
*_Message*<br/>
Описательное сообщение об ошибке.  
  
## <a name="see-also"></a>См. также  
 [пространство имен Concurrency](concurrency-namespace.md)   
 [Асинхронные блоки сообщений](../../../parallel/concrt/asynchronous-message-blocks.md)



