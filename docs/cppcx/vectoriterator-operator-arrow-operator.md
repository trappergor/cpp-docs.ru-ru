---
title: "Оператор VectorIterator::operator-&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator::operator->"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Оператор VectorIterator::operator->"
ms.assetid: d6caed5c-4899-45f8-95a2-687eafeeb8e1
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Оператор VectorIterator::operator-&gt;
Извлекает адрес элемента, на который ссылается текущий итератор VectorIterator.  
  
## Синтаксис  
  
```  
Detail::ArrowProxy<T> operator->() const;  
```  
  
## Возвращаемое значение  
 Значение элемента, на который ссылается текущий итератор VectorIterator.  
  
 Тип возвращаемого значения является неуказанным внутренним типом, необходимым для реализации этого оператора.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::VectorIterator](../cppcx/platform-collections-vectoriterator-class.md)