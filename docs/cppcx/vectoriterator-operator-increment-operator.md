---
title: "Оператор VectorIterator::operator++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator++"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Оператор VectorIterator::operator++"
ms.assetid: c46b18ff-45be-436a-8f31-b3a5ecc19b77
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Оператор VectorIterator::operator++
Выполняет увеличение текущего итератора VectorIterator.  
  
## Синтаксис  
  
```  
  
VectorIterator& operator++();  
VectorIterator operator++(  
   int  
);  
```  
  
## Возвращаемое значение  
 Первый синтаксис выполняет увеличение текущего итератора VectorIterator и возвращает его. Второй синтаксис возвращает копию текущего итератора VectorIterator, а затем выполняет увеличение текущего итератора VectorIterator.  
  
## Заметки  
 Первый синтаксис выполняет увеличение текущего итератора VectorIterator перед его использованием.  
  
 Второй синтаксис выполняет увеличение текущего итератора VectorIterator после его использования. Тип `int` во втором примере синтаксиса задает операцию увеличения после использования, он не является операндом целочисленного типа.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md)