---
title: "VectorIterator::operatorOperator | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator[]"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Оператор VectorIterator::operator[]"
ms.assetid: e1ba8101-8c16-4be1-b31b-91099d6e81f3
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operatorOperator
Извлекает ссылку на элемент, отстоящий от текущего итератора VectorIterator на указанную величину смещения.  
  
## Синтаксис  
  
```  
  
reference operator[](difference_type n) const;  
```  
  
#### Параметры  
 `n`  
 Целочисленная величина смещения.  
  
## Возвращаемое значение  
 Элемент, отстоящий от текущего итератора VectorIterator на `n` элементов.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md)