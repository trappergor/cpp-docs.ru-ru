---
title: "VectorViewIterator::operator- - оператор | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator-"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorViewIterator::operator- - оператор"
ms.assetid: 03935872-8acc-4919-ae14-f375ca738aac
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorViewIterator::operator- - оператор
Вычитает указанное количество элементов из текущего итератора, возвращая новый итератор, или вычитает указанный итератор из текущего итератора, возвращая количество элементов между итераторами.  
  
## Синтаксис  
  
```  
  
VectorViewIterator operator-(  
   difference_type n  
) const;  
  
difference_type operator-(  
   const VectorViewIterator& other  
) const;  
```  
  
#### Параметры  
 `n`  
 Количество элементов.  
  
 `other`  
 Другой объект VectorViewIterator.  
  
## Возвращаемое значение  
 Синтаксис первого оператора возвращает объект VectorViewIterator, количество элементов которого меньше, чем у текущего объекта VectorViewIterator, на `n`. Синтаксис второго оператора возвращает количество элементов между текущим объектом VectorViewIterator и другим объектом VectorViewIterator, заданным параметром `other`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md)