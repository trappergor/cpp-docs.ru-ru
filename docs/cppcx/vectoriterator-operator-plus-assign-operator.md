---
title: "VectorIterator::operator+= - оператор | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator+="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator+= - оператор"
ms.assetid: 9fd0d8a9-29ae-439a-b6ee-39e8fcf225ec
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator+= - оператор
Увеличивает текущий итератор VectorIterator на указанную величину смещения.  
  
## Синтаксис  
  
```  
VectorIterator& operator+=(  
   difference_type n  
);  
```  
  
#### Параметры  
 `n`  
 Целочисленная величина смещения.  
  
## Возвращаемое значение  
 Обновленный VectorIterator.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md)