---
title: Класс accelerator_view_removed | Документация Майкрософт
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
ms.openlocfilehash: f1c8963fee0fa7718c6ea8fe67904613b2dca8ad
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020264"
---
# <a name="acceleratorviewremoved-class"></a>Класс accelerator_view_removed
Исключение, возникающее при сбое основного вызова DirectX из-за механизм обнаружения и восстановления времени ожидания Windows.  
  
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

Инициализирует новый экземпляр класса [accelerator_view_removed](accelerator-view-removed-class.md) класса.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
explicit accelerator_view_removed(  
    const char * _Message,  
    HRESULT _View_removed_reason ) throw();  
  
explicit accelerator_view_removed(  
    HRESULT _View_removed_reason ) throw();  
```  
  
### <a name="parameters"></a>Параметры  
*_Message*<br/>
Описание ошибки.  
  
*_View_removed_reason*<br/>
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
