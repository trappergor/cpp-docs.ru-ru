---
title: "Оператор VectorViewIterator::operator== | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Оператор VectorViewIterator::operator=="
ms.assetid: 89534116-5035-413b-89d3-073eedb88337
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Оператор VectorViewIterator::operator==
Указывает, равен ли текущий объект VectorViewIterator указанному объекту VectorViewIterator.  
  
## Синтаксис  
  
```  
bool operator==(  
   const VectorViewIterator& other  
) const;  
```  
  
#### Параметры  
 `other`  
 Другой объект VectorViewIterator.  
  
## Возвращаемое значение  
 Значение `true`, если текущий объект VectorViewIterator равен объекту `other`, в противном случае — значение `false`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md)