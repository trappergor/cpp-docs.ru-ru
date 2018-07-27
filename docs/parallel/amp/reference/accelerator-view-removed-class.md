---
title: Класс accelerator_view_removed | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0426dd44cfcb8f655f3981802dfe23adcd436a0d
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33688158"
---
# <a name="acceleratorviewremoved-class"></a>Класс accelerator_view_removed
Исключение, возникающее при сбое внутренний вызов DirectX из-за механизм обнаружения и восстановления Windows время ожидания.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class accelerator_view_removed : public runtime_exception;  
```  
  
## <a name="members"></a>Участники  
  
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

## <a name="ctor"></a> accelerator_view_removed 

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
  
## <a name="get_view_removed_reason_method"></a> get_view_removed_reason 

Возвращает код ошибки HRESULT, указывающее причину `accelerator_view` удаления объекта.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
HRESULT get_view_removed_reason() const throw();  
```  
  
 
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
