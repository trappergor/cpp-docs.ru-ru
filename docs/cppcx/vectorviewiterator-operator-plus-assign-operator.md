---
title: "VectorViewIterator::operator+= - оператор | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator+="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator+= - оператор"
ms.assetid: 2009e54e-a4f2-444a-b729-a1b6b8b707bb
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator+= - оператор
Увеличивает текущий итератор VectorViewIterator на указанную величину смещения.  
  
## Синтаксис  
  
```  
VectorViewIterator& operator+=(  
   difference_type n  
);  
```  
  
#### Параметры  
 `n`  
 Целочисленная величина смещения.  
  
## Возвращаемое значение  
 Обновленный VectorViewIterator.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md)