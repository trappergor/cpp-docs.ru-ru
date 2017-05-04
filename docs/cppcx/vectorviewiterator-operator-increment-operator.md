---
title: "VectorViewIterator::operator++ - оператор | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator++"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator++ - оператор"
ms.assetid: 5391e6e2-a7ee-4dab-8cee-b2237894246f
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator++ - оператор
Выполняет приращение текущего итератора VectorViewIterator.  
  
## Синтаксис  
  
```  
  
VectorViewIterator& operator++();  
VectorViewIterator operator++(  
   int  
);  
```  
  
## Возвращаемое значение  
 Первый синтаксис выполняет приращение текущего итератора VectorViewIterator и возвращает его. Второй синтаксис возвращает копию текущего итератора VectorViewIterator, а затем выполняет приращение текущего итератора VectorViewIterator.  
  
## Заметки  
 Первый синтаксис выполняет приращение текущего итератора VectorViewIterator перед его использованием.  
  
 Второй синтаксис выполняет приращение текущего итератора VectorViewIterator после его использования. Тип `int` во втором примере синтаксиса задает операцию увеличения после использования, он не является операндом целочисленного типа.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md)