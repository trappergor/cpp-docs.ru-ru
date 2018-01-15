---
title: "Класс runtime_exception | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- runtime_exception
- AMPRT/runtime_exception
- AMPRT/Concurrency::runtime_exception
- AMPRT/Concurrency::runtime_exception::get_error_code
dev_langs: C++
helpviewer_keywords: runtime_exception class
ms.assetid: 8fe3ce2c-3d4c-4b9c-95e8-e592f37adefd
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 705949f118e85b6dfef2beeccb55fecd63a64882
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="runtimeexception-class"></a>runtime_exception - класс
Базовый тип для исключений C++ Accelerated Massive параллелизма (AMP) библиотеки.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
class runtime_exception : public std::exception;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор runtime_exception](#ctor)|Инициализирует новый экземпляр класса `runtime_exception`.|  
|[~ runtime_exception деструктор](#dtor)|Уничтожает `runtime_exception` объекта.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[get_error_code](#runtime_exception__get_error_code)|Возвращает код ошибки, которая вызвала исключение.|  

  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[оператор=](#operator_eq)|Копирует содержимое указанного `runtime_exception` объекта в другой.|  
  
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
 HRESULT ошибки, вызвавшей исключение.  
  
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
Возвращает код ошибки, которая вызвала исключение.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
HRESULT get_error_code() const throw();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 HRESULT ошибки, вызвавшей исключение.  
  
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
