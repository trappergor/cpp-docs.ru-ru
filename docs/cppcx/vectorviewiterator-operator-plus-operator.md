---
title: "VectorViewIterator::operator+ - оператор | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator+"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator+ - оператор"
ms.assetid: 8206de2f-61b3-49cd-9715-d57695d880b3
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator+ - оператор
Возвращает объект VectorViewIterator, указывающий на элемент с заданным смещением от указанного объекта VectorViewIterator.  
  
## Синтаксис  
  
```  
  
VectorViewIterator operator+(  
   difference_type n  
) const;  
  
template <  
   typename T  
>   
inline VectorViewIterator<T> operator+  
   (ptrdiff_t n,   
   const VectorViewIterator<T>& i  
);  
  
```  
  
#### Параметры  
 `T`  
 Во втором синтаксисе — имя типа объекта VectorViewIterator.  
  
 `n`  
 Целочисленная величина смещения.  
  
 `i`  
 Во втором синтаксисе — объект VectorViewIterator.  
  
## Возвращаемое значение  
 В первом синтаксисе — объект VectorViewIterator, указывающий на элемент с заданным смещением от текущего объекта VectorViewIterator.  
  
 Во втором синтаксисе — объект VectorViewIterator, указывающий на элемент с заданным смещением от начала `i` параметра.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md)