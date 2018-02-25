---
title: "Класс runtime_exception | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 678f0a93577a6e30afbc5e0c6d83aca6b6a7bedc
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
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

## <a name="runtime_exception__ctor">Конструктор runtime_exception</a>  
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

## <a name="dtor">~ runtime_exception деструктор</a>  
Удаляет объект.  
  
### <a name="syntax"></a>Синтаксис  
  
```  
virtual ~runtime_exception() throw();  
```  
  
## <a name="runtime_exception__get_error_code"></a>  get_error_code   
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
