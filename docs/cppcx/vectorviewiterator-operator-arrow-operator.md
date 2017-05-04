---
title: "Оператор VectorViewIterator::operator-&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator::operator->"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Оператор VectorViewIterator::operator->"
ms.assetid: cc02cfa2-dfcb-4fb7-b4a0-c290f91aa4a6
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Оператор VectorViewIterator::operator-&gt;
Извлекает адрес элемента, на который ссылается текущий итератор VectorViewIterator.  
  
## Синтаксис  
  
```  
Detail::ArrowProxy<T> operator->() const;  
```  
  
## Возвращаемое значение  
 Значение элемента, на который ссылается текущий итератор VectorViewIterator.  
  
 Тип возвращаемого значения является неуказанным внутренним типом, необходимым для реализации этого оператора.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md)