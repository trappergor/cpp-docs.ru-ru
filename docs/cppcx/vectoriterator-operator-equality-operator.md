---
title: "VectorIterator::operator== - оператор | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator== - оператор"
ms.assetid: 1152153c-a564-40bb-8924-a3c6a0ea3752
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator== - оператор
Указывает, равен ли текущий объект VectorIterator указанному объекту VectorIterator.  
  
## Синтаксис  
  
```  
bool operator==(  
   const VectorIterator& other  
) const;  
```  
  
#### Параметры  
 `other`  
 Другой объект VectorIterator.  
  
## Возвращаемое значение  
 Значение `true`, если текущий объект VectorIterator равен объекту `other`, в противном случае — значение `false`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md)