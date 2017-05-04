---
title: "Метод Vector::SetAt | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::SetAt"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::SetAt"
ms.assetid: ddfb454e-dbfd-4831-b040-674b085d8fb6
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод Vector::SetAt
Присваивает указанное значение к элементу текущего объекта Vector, определяемому заданным индексом.  
  
## Синтаксис  
  
```  
  
virtual void SetAt(  
   unsigned int index,   
   T item  
);  
```  
  
#### Параметры  
 `index`  
 Целое значение без знака, отсчитываемое от нуля, которое указывает определенный элемент в объекте Vector.  
  
 `item`  
 Значение, присваиваемое указанному элементу. Тип элемента `item` определяется именем типа *T*.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md)