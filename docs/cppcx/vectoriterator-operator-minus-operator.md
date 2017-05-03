---
title: "VectorIterator::operator- - оператор | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator-"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator- - оператор"
ms.assetid: 5714c132-e973-47fd-901b-ba13da7b9372
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator- - оператор
Вычитает указанное количество элементов из текущего итератора, возвращая новый итератор, или вычитает указанный итератор из текущего итератора, возвращая количество элементов между итераторами.  
  
## Синтаксис  
  
```  
  
VectorIterator operator-(  
   difference_type n  
) const;  
  
difference_type operator-(  
   const VectorIterator& other  
) const;  
```  
  
#### Параметры  
 `n`  
 Количество элементов.  
  
 `other`  
 Другой объект VectorIterator.  
  
## Возвращаемое значение  
 Синтаксис первого оператора возвращает объект VectorIterator, количество элементов которого меньше, чем у текущего объекта VectorIterator, на `n`. Синтаксис второго оператора возвращает количество элементов между текущим объектом VectorIterator и другим объектом VectorIterator, заданным параметром `other`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md)