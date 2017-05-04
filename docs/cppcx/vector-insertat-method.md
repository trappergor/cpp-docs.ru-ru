---
title: "Метод Vector::InsertAt | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::InsertAt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::InsertAt"
ms.assetid: 05b2ca08-234e-4fc0-acfd-cafa148d1577
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод Vector::InsertAt
Вставляет указанный элемент в текущий объект Vector после элемента, указанного заданным индексом.  
  
## Синтаксис  
  
```  
  
virtual void InsertAt(  
   unsigned int index,   
   T item)  
```  
  
#### Параметры  
 `index`  
 Целое значение без знака, отсчитываемое от нуля, которое указывает определенный элемент в объекте Vector.  
  
 `item`  
 Элемент, который требуется вставить в объект Vector после элемента, указанного параметром `index`. Тип элемента `item` определяется именем типа *T*.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md)