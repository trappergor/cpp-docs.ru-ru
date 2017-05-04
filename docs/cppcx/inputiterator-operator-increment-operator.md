---
title: "InputIterator::operator++ - оператор | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::InputIterator::operator++"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InputIterator::operator++ - оператор"
ms.assetid: 50781585-7a12-4f02-bff8-68fe0adf0693
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# InputIterator::operator++ - оператор
Выполняет приращение текущего итератора InputIterator.  
  
## Синтаксис  
  
```  
  
InputIterator& operator++();  
  
InputIterator operator++(  
   int  
);  
```  
  
## Возвращаемое значение  
 Первый синтаксис выполняет приращение текущего итератора InputIterator и возвращает его. Второй синтаксис возвращает копию текущего итератора InputIterator, а затем выполняет приращение текущего итератора InputIterator.  
  
## Заметки  
 Первый синтаксис InputIterator выполняет приращение текущего итератора InputIterator перед его использованием.  
  
 Второй синтаксис выполняет приращение текущего итератора InputIterator после его использования. Тип `int` во втором примере синтаксиса задает операцию увеличения после использования, он не является операндом целочисленного типа.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::InputIterator](../cppcx/platform-collections-inputiterator-class.md)