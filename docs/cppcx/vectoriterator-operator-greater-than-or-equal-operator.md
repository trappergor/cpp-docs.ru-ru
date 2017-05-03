---
title: "VectorIterator::operator&gt;= - оператор | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator>="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator>= - оператор"
ms.assetid: 8154015e-8da7-4381-8128-d3669eb88e16
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator&gt;= - оператор
Указывает, является ли текущий объект VectorIterator большим или равным указанному объекту VectorIterator.  
  
## Синтаксис  
  
```cpp  
  
bool operator>=(  
   const VectorIterator& other  
) const   
```  
  
#### Параметры  
 `other`  
 Другой объект VectorIterator.  
  
## Возвращаемое значение  
 Значение `true`, если текущий объект VectorIterator больше или равен объекту `other`, в противном случае — значение `false`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md)