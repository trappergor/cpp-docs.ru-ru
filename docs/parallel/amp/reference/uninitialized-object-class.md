---
title: Класс uninitialized_object | Документы Microsoft
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
ms.openlocfilehash: 9b9b10af535b0739d480326d616ee7587318bb5a
ms.sourcegitcommit: 7019081488f68abdd5b2935a3b36e2a5e8c571f8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2018
ms.locfileid: "33696179"
---
# <a name="uninitializedobject-class"></a>uninitialized_object - класс
Исключение, возникающее при использовании неинициализированного объекта.  
  
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
 `_Message`  
 Описание ошибки.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `unsupported_feature`. 

## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)
