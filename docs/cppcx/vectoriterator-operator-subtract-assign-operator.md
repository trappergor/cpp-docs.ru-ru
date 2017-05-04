---
title: "VectorIterator::operator-= - оператор | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator-="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator-= - оператор"
ms.assetid: 30bcf93c-4760-410d-b344-09741be10069
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator-= - оператор
Уменьшает текущий итератор VectorIterator на указанную величину смещения.  
  
## Синтаксис  
  
```  
VectorIterator& operator-=(  
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