---
title: "Оператор VectorIterator::operator!= | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator!="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Оператор VectorIterator::operator!="
ms.assetid: 88b71c7e-9c88-4282-a518-455059da16c2
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Оператор VectorIterator::operator!=
Указывает, отличен ли текущий объект VectorIterator от указанного объекта VectorIterator.  
  
## Синтаксис  
  
```  
bool operator!=(  
   const VectorIterator& other  
) const;  
```  
  
#### Параметры  
 `other`  
 Другой объект VectorIterator.  
  
## Возвращаемое значение  
 Значение `true`, если текущий объект VectorIterator не равен объекту `other`, в противном случае — значение `false`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md)