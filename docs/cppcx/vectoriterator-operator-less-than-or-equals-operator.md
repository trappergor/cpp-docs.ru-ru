---
title: "VectorIterator::operator&lt;= - оператор | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator<="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorIterator::operator<= - оператор"
ms.assetid: 57d3c269-77a5-4731-a3b4-dcda2758da19
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorIterator::operator&lt;= - оператор
Указывает, является ли текущий объект VectorIterator меньшим или равным указанному объекту VectorIterator.  
  
## Синтаксис  
  
```cpp  
  
bool operator<=(  
   const VectorIterator& other  
) const   
```  
  
#### Параметры  
 `other`  
 Другой объект VectorIterator.  
  
## Возвращаемое значение  
 Значение `true`, если текущий объект VectorIterator меньше или равен объекту `other`, в противном случае — значение `false`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md)