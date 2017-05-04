---
title: "VectorViewIterator::operator-= - оператор | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator-="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator-= - оператор"
ms.assetid: fc4d5f19-a001-44fd-aabe-972d8b54ca2f
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator-= - оператор
Уменьшает текущий итератор VectorIterator на указанную величину смещения.  
  
## Синтаксис  
  
```  
VectorViewIterator& operator-=(  
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
 [Класс Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md)