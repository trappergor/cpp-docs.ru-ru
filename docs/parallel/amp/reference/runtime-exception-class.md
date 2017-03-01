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
- amp/Concurrency::direct3d_abort
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 1a2655ed4c8783dd5f7a3b8af2a7d6a9db88f43e
ms.lasthandoff: 02/24/2017

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
|[get_error_code метод](#runtime_exception__get_error_code)|Возвращает код ошибки, вызвавшей исключение.|  

  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[оператор =-оператор](#operator_eq)|Копирует содержимое указанного `runtime_exception` объекта в другой.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `exception`  
  
 `runtime_exception`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** amprt.h  
  
 **Пространство имен** : Concurrency  

## <a name="a-nameruntimeexceptionctora--runtimeexception-constructor"></a><a name="runtime_exception__ctor"></a>Конструктор runtime_exception  
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

## <a name="a-namedtora--runtimeexception-destructor"></a><a name="dtor"></a>~ runtime_exception деструктор  
Удаляет объект.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
virtual ~runtime_exception() throw();  
```  
  
## <a name="a-nameruntimeexceptiongeterrorcodea--geterrorcode"></a><a name="runtime_exception__get_error_code"></a>get_error_code   
Возвращает код ошибки, вызвавшей исключение.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
HRESULT get_error_code() const throw();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение HRESULT ошибки, вызвавшей исключение.  
  
## <a name="a-nameruntimeexceptionoperatoreqa--operator"></a><a name="runtime_exception__operator_eq"></a>  оператор=   
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

