---
title: "VectorIterator::operator-- - оператор | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator--"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator-- - оператор"
ms.assetid: 650a3037-2984-4110-9d7c-cd3756e5f4b9
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator-- - оператор
Выполняет уменьшение текущего итератора VectorIterator.  
  
## Синтаксис  
  
```  
  
VectorIterator& operator--();  
VectorIterator operator--(  
   int  
);  
```  
  
## Возвращаемое значение  
 Первый синтаксис выполняет уменьшение текущего итератора VectorIterator и возвращает его. Второй синтаксис возвращает копию текущего итератора VectorIterator, а затем выполняет уменьшение текущего итератора VectorIterator.  
  
## Заметки  
 Первый синтаксис выполняет уменьшение текущего итератора VectorIterator перед его использованием.  
  
 Второй синтаксис выполняет уменьшение текущего итератора VectorIterator после его использования. Тип `int` во втором примере синтаксиса указывает операцию уменьшения после использования, он не является операндом целочисленного типа.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md)