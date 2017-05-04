---
title: "VectorViewIterator::operatorOperator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator[]"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator[] - оператор"
ms.assetid: 41bf327d-2037-457c-83df-6338fc1abbc2
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operatorOperator
Извлекает ссылку на элемент, удаленный от текущего итератора VectorViewIterator на указанную величину смещения.  
  
## Синтаксис  
  
```  
reference operator[](difference_type n) const;  
```  
  
#### Параметры  
 `n`  
 Целочисленная величина смещения.  
  
## Возвращаемое значение  
 Элемент, удаленный от текущего итератора VectorViewIterator на `n`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md)