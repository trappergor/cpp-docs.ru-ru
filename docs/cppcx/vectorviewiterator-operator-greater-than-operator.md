---
title: "Метод VectorViewIterator::operator&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Метод VectorViewIterator::operator>"
ms.assetid: c689b677-e3c6-4f6e-8e3a-54d5f2a6123d
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод VectorViewIterator::operator&gt;
Указывает, действительно ли текущий объект VectorViewIterator больше, чем указанный объект VectorViewIterator.  
  
## Синтаксис  
  
```  
  
bool operator>(  
   const VectorViewIterator& other  
) const;  
```  
  
#### Параметры  
 `other`  
 Другой объект VectorViewIterator.  
  
## Возвращаемое значение  
 Значение `true`, если текущий объект VectorViewIterator больше объекта `other`; в противном случае — значение `false`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md)