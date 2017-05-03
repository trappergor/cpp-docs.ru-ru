---
title: "VectorIterator::operator+ - оператор | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator+"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator+ - оператор"
ms.assetid: 5e907537-7d10-4766-a412-e7ea08b3456a
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator+ - оператор
Возвращает объект VectorIterator, указывающий на элемент с заданным смещением от указанного объекта VectorIterator.  
  
## Синтаксис  
  
```  
  
VectorIterator operator+(  
   difference_type n) ;  
  
template <  
   typename T  
>  
inline VectorIterator<T> operator+(  
   ptrdiff_t n,  
   const VectorIterator<T>& i  
);  
  
```  
  
#### Параметры  
 `T`  
 Во втором синтаксисе — имя типа объекта VectorIterator.  
  
 `n`  
 Целочисленная величина смещения.  
  
 `i`  
 Во втором синтаксисе — объект VectorIterator.  
  
## Возвращаемое значение  
 В первом синтаксисе — объект VectorIterator, указывающий на элемент с заданным смещением от текущего объекта VectorIterator.  
  
 Во втором синтаксисе — объект VectorIterator, указывающий на элемент с заданным смещением от начала параметра `i`.  
  
## Заметки  
 Первый пример синтаксиса  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [\(NOTINBUILD\) Пространство имен Platform](http://msdn.microsoft.com/ru-ru/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)