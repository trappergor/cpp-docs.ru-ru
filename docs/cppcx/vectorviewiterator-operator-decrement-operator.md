---
title: "Оператор VectorViewIterator::operator-- | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator--"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Оператор VectorViewIterator::operator--"
ms.assetid: edf3ba42-1fa4-4795-9a37-1f7dfb23ad19
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Оператор VectorViewIterator::operator--
Выполняет уменьшение текущего итератора VectorViewIterator.  
  
## Синтаксис  
  
```  
VectorViewIterator& operator--();  
VectorViewIterator operator--(  
   int  
);  
```  
  
## Возвращаемое значение  
 Первый синтаксис выполняет уменьшение текущего итератора VectorViewIterator и возвращает его. Второй синтаксис возвращает копию текущего итератора VectorViewIterator, а затем выполняет уменьшение текущего итератора VectorViewIterator.  
  
## Заметки  
 Первый синтаксис выполняет уменьшение текущего итератора VectorViewIterator перед его использованием.  
  
 Второй синтаксис выполняет уменьшение текущего итератора VectorViewIterator после его использования. Тип `int` во втором синтаксисе указывает операцию уменьшения после использования, а не фактический операнд целочисленного типа.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md)