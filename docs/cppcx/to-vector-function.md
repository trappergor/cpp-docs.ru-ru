---
title: "Функция to_vector | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Windows::Foundation::Collections::to_vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Функция to_vector"
ms.assetid: 9cdd5123-7243-4def-a1d3-162e0bf6219e
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 3
---
# Функция to_vector
Возвращает объект `std::vector`, значение которого совпадает с коллекцией, лежащей в основе указанного параметра IVector или IVectorView.  
  
## Синтаксис  
  
```  
template <  
   typename T  
>  
inline ::std::vector<T> to_vector(  
   IVector<T>^ v  
);  
template <  
   typename T  
>  
inline ::std::vector<T> to_vector(  
   IVectorView<T>^ v  
);  
```  
  
#### Параметры  
 `T`  
 Параметр типа шаблона.  
  
 `v`  
 Интерфейс IVector или IVectorView, который предоставляет доступ к базовому объекту Vector или VectorView.  
  
## Возвращаемое значение  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Windows::Foundation::Collections  
  
## См. также  
 [Пространство имен Windows::Foundation::Collections](../cppcx/windows-foundation-collections-namespace-c-cx.md)