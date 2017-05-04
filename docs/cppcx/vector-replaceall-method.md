---
title: "Метод Vector::ReplaceAll | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::ReplaceAll"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::ReplaceAll"
ms.assetid: dec905f9-80fc-4aa0-ad04-bbab10feb0b2
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод Vector::ReplaceAll
Удаляет элементы из текущего объекта Vector, а затем вставляет элементы из указанного массива.  
  
## Синтаксис  
  
```  
  
virtual void ReplaceAll(  
   const ::Platform::Array<T>^ arr  
);  
```  
  
#### Параметры  
 `arr`  
 Массив объектов, тип которых определяется именем типа *T*.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md)