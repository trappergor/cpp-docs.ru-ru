---
title: "BackInsertIterator::operator++ - оператор | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::BackInsertIterator::operator++"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BackInsertIterator::operator++ - оператор"
ms.assetid: 08324574-db2b-4d95-825e-a93a56f327da
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# BackInsertIterator::operator++ - оператор
Возвращает ссылку на текущий объект BackInsertIterator. Итератор не изменяется.  
  
## Синтаксис  
  
```  
  
BackInsertIterator& operator++();  
  
BackInsertIterator operator++(  
   int  
);  
```  
  
## Возвращаемое значение  
 Ссылка на текущий объект BackInsertIterator.  
  
## Заметки  
 Выражение в первом примере синтаксиса увеличивает значение текущего элемента BackInsertIterator перед его использованием, а во втором — после его использования. Тип `int` во втором примере синтаксиса задает операцию увеличения после использования, он не является операндом целочисленного типа.  
  
 Впрочем, этот оператор не изменяет объект BackInsertIterator. Вместо этого он возвращает ссылку на текущий итератор, остающийся неизменным. Это поведение аналогично поведению оператора [operator\*](../cppcx/backinsertiterator-operator-dereference-operator.md).  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::BackInsertIterator](../cppcx/platform-collections-backinsertiterator-class.md)