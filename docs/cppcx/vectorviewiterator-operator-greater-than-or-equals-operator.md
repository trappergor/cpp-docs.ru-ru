---
title: "VectorViewIterator::operator&gt;= - оператор | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator>="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator>= - оператор"
ms.assetid: 506fbf12-a28f-4695-a5a4-418341dec806
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator&gt;= - оператор
Указывает, является ли текущий объект VectorViewIterator большим или равным указанному объекту VectorViewIterator.  
  
## Синтаксис  
  
```  
  
bool operator>=(  
   const VectorViewIterator& other  
) const;  
```  
  
#### Параметры  
 `other`  
 Другой объект VectorViewIterator.  
  
## Возвращаемое значение  
 Значение `true`, если текущий объект VectorViewIterator больше или равен объекту `other`, в противном случае — значение `false`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md)