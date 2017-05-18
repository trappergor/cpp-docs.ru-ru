---
title: "Класс scheduler_resource_allocation_error | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error::scheduler_resource_allocation_error
- CONCRT/concurrency::scheduler_resource_allocation_error::get_error_code
dev_langs:
- C++
helpviewer_keywords:
- scheduler_resource_allocation_error class
ms.assetid: 8b40449a-7abb-4d0a-bb85-c0e9a495ae97
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
ms.openlocfilehash: 84f32bb6192057c9d5872147cc8ef0bd2c13b349
ms.contentlocale: ru-ru
ms.lasthandoff: 03/17/2017

---
# <a name="schedulerresourceallocationerror-class"></a>Класс scheduler_resource_allocation_error
Этот класс описывает исключение, возникающее из-за сбоя получения критического ресурса в исполняющей среде с параллелизмом.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class scheduler_resource_allocation_error : public std::exception;
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[scheduler_resource_allocation_error](#ctor)|Перегружен. Создает объект `scheduler_resource_allocation_error`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[get_error_code](#get_error_code)|Возвращает код ошибки, вызвавшей исключение.|  
  
## <a name="remarks"></a>Примечания  
 Это исключение обычно вызывается при сбое вызова операционной системы в среде выполнения с параллелизмом. Код ошибки, который обычно возвращается из вызова метода Win32 `GetLastError`, преобразуется в значение типа `HRESULT` и может быть получен посредством метода `get_error_code`.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `scheduler_resource_allocation_error`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** concrt.h  
  
 **Пространство имен:** concurrency  
  
##  <a name="get_error_code"></a>get_error_code 

 Возвращает код ошибки, вызвавшей исключение.  
  
```
HRESULT get_error_code() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 `HRESULT` Значение ошибки, вызвавшей исключение.  
  
##  <a name="ctor"></a>scheduler_resource_allocation_error 

 Создает объект `scheduler_resource_allocation_error`.  
  
```
scheduler_resource_allocation_error(
    _In_z_ const char* _Message,
    HRESULT _Hresult) throw();

explicit _CRTIMP scheduler_resource_allocation_error(
    HRESULT _Hresult) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `_Message`  
 Описательное сообщение об ошибке.  
  
 `_Hresult`  
 `HRESULT` Значение ошибки, вызвавшей исключение.  
  
## <a name="see-also"></a>См. также  
 [Пространство имен concurrency](concurrency-namespace.md)

