---
title: "Оператор VectorIterator::operator&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Оператор VectorIterator::operator>"
ms.assetid: a9a323a4-d28a-4080-a48c-ed4c8ef2eafb
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Оператор VectorIterator::operator&gt;
Указывает, действительно ли текущий объект VectorIterator больше, чем указанный объект VectorIterator.  
  
## Синтаксис  
  
```cpp  
  
bool operator>(  
   const VectorIterator& other  
) const   
```  
  
#### Параметры  
 `other`  
 Другой объект VectorIterator.  
  
## Возвращаемое значение  
 Значение `true`, если текущий объект VectorIterator больше объекта `other`; в противном случае — значение `false`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md)