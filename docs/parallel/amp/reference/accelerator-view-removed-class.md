---
title: "Класс accelerator_view_removed | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- accelerator_view_removed
- AMPRT/accelerator_view_removed
- AMPRT/Concurrency::accelerator_view_removed:accelerator_view_removed
- AMPRT/Concurrency::accelerator_view_removed:get_view_removed_reason
dev_langs:
- C++
helpviewer_keywords:
- AMPRT/Concurrency::accelerator_view_removed:accelerator_view_removed Class
ms.assetid: 262446de-311c-454e-a5ed-e2aaced0d88a
caps.latest.revision: 6
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 5faef5bd1be6cc02d6614a6f6193c74167a8ff23
ms.openlocfilehash: c45eb8192266999c8771f6788de16859fe7a12c8
ms.lasthandoff: 03/17/2017

---
# <a name="acceleratorviewremoved-class"></a>Класс accelerator_view_removed
Исключение, возникающее при сбое внутренний вызов DirectX из-за механизм обнаружения и восстановления Windows время ожидания.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class accelerator_view_removed : public runtime_exception;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор accelerator_view_removed](#ctor)|Инициализирует новый экземпляр класса `accelerator_view_removed`.|  

### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[get_view_removed_reason](#get_view_removed_reason)|Возвращает код ошибки HRESULT, указывающее причину `accelerator_view` удаления объекта.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `runtime_exception`  
  
 `out_of_memory`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amprt.h  
  
 **Пространство имен** : Concurrency  

## <a name="ctor"></a>accelerator_view_removed 

Инициализирует новый экземпляр [accelerator_view_removed](accelerator-view-removed-class.md) класса.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
explicit accelerator_view_removed(  
    const char * _Message,  
    HRESULT _View_removed_reason ) throw();  
  
explicit accelerator_view_removed(  
    HRESULT _View_removed_reason ) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `_Message`  
 Описание ошибки.  
  
 `_View_removed_reason`  
 Код ошибки HRESULT, указывающее причину удаления `accelerator_view` объекта.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Новый экземпляр класса accelerator_view_removed.  
  
## <a name="get_view_removed_reason_method"></a>get_view_removed_reason 

Возвращает код ошибки HRESULT, указывающее причину `accelerator_view` удаления объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
HRESULT get_view_removed_reason() const throw();  
```  
  
 
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)

