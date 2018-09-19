---
title: Класс uninitialized_object | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-amp
ms.topic: reference
f1_keywords:
- uninitialized_object
- AMPRT/uninitialized_object
- AMPRT/Concurrency::uninitialized_object
dev_langs:
- C++
helpviewer_keywords:
- uninitialized_object class
ms.assetid: 6ae3c4e8-64a6-4511-a158-03be197b63af
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 821f3c25d195a2c92ac04fdf5f9e5a59b493c257
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46113842"
---
# <a name="uninitializedobject-class"></a>uninitialized_object - класс
Исключение, возникающее, когда используется неинициализированный объект.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class uninitialized_object : public runtime_exception;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[uninitialized_object, конструктор](#ctor)|Инициализирует новый экземпляр класса `uninitialized_object`.|  

  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `runtime_exception`  
  
 `uninitialized_object`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amprt.h  
  
 **Пространство имен** : Concurrency  
## <a name="uninitialized_object__ctor"></a> unsupported_feature 

Создает новый экземпляр исключения unsupported_feature.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
explicit unsupported_feature(  
    const char * _Message ) throw();  
  
unsupported_feature() throw();  
```  
  
### <a name="parameters"></a>Параметры  
*_Message*<br/>
Описание ошибки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `unsupported_feature`. 

## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
