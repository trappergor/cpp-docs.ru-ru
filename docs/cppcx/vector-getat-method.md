---
title: "Vector::GetAt - метод | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::GetAt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::GetAt - метод"
ms.assetid: 3766b399-cef2-4006-9a87-50f717390cac
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::GetAt - метод
Извлекает элемент текущего объекта Vector, указанный заданным индексом.  
  
## Синтаксис  
  
```  
  
virtual T GetAt(  
   unsigned int index  
);  
```  
  
#### Параметры  
 `index`  
 Целое значение без знака, отсчитываемое от нуля, которое указывает определенный элемент в объекте Vector.  
  
## Возвращаемое значение  
 Элемент, заданный параметром `index`. Тип элемента определяется именем типа *T*.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md)