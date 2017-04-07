---
title: "Класс runtime_exception | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- runtime_exception
- AMPRT/runtime_exception
- AMPRT/Concurrency::runtime_exception
- AMPRT/Concurrency::runtime_exception::get_error_code
dev_langs:
- C++
helpviewer_keywords:
- runtime_exception class
ms.assetid: 8fe3ce2c-3d4c-4b9c-95e8-e592f37adefd
caps.latest.revision: 10
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
ms.openlocfilehash: 399d2531c06285012df12d703b4cda6e18469c38
ms.lasthandoff: 03/17/2017

---
# <a name="runtimeexception-class"></a>Класс runtime_exception
Базовый тип для исключения в библиотеке C++ Accelerated больших параллелизма (AMP).  
  
### <a name="syntax"></a>Синтаксис  
  
```  
class runtime_exception : public std::exception;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор runtime_exception](#ctor)|Инициализирует новый экземпляр класса `runtime_exception`.|  
|[~ runtime_exception деструктор](#dtor)|Уничтожает `runtime_exception` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[get_error_code](#runtime_exception__get_error_code)|Возвращает код ошибки, вызвавшей исключение.|  

  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[operator=](#operator_eq)|Копирует содержимое указанного `runtime_exception` объекта в другой.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `runtime_exception`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amprt.h  
  
 **Пространство имен** : Concurrency  

## <a name="runtime_exception__ctor"></a>Конструктор runtime_exception  
Инициализирует новый экземпляр класса.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
runtime_exception(  
    const char * _Message,  
    HRESULT _Hresult ) throw();  
  
explicit runtime_exception(  
    HRESULT _Hresult ) throw();  
  
runtime_exception(  
    const runtime_exception & _Other ) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `_Message`  
 Описание ошибки, вызвавшей исключение.  
  
 `_Hresult`  
 Значение HRESULT ошибки, вызвавшей исключение.  
  
 `_Other`  
 `runtime_exception` Объект, подлежащий копированию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `runtime_exception`.  

## <a name="dtor"></a>~ runtime_exception деструктор  
Удаляет объект.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
virtual ~runtime_exception() throw();  
```  
  
## <a name="runtime_exception__get_error_code"></a>get_error_code   
Возвращает код ошибки, вызвавшей исключение.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
HRESULT get_error_code() const throw();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение HRESULT ошибки, вызвавшей исключение.  
  
## <a name="runtime_exception__operator_eq"></a>  оператор=   
  Копирует содержимое указанного `runtime_exception` объекта в другой.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
runtime_exception & operator= (    const runtime_exception & _Other ) throw();  
```  
  
### <a name="parameters"></a>Параметры  
 `_Other`  
 `runtime_exception` Объект, подлежащий копированию.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на это `runtime_exception` объекта.  
  

  
## <a name="see-also"></a>См. также  
 [Пространство имен Concurrency (C++ AMP)](concurrency-namespace-cpp-amp.md)

