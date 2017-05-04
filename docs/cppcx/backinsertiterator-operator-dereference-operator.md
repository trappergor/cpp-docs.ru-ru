---
title: "BackInsertIterator::operator* - оператор | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::BackInsertIterator::operator*"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BackInsertIterator::operator* - оператор"
ms.assetid: 68d70bc8-da84-49c6-ba35-4ac5aa6dad16
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# BackInsertIterator::operator* - оператор
Получает ссылку на текущий объект BackInsertIterator.  
  
## Синтаксис  
  
```  
BackInsertIterator& operator*();  
```  
  
## Возвращаемое значение  
 Ссылка на текущий объект BackInsertIterator.  
  
## Заметки  
 Этот оператор возвращает ссылку на текущий BackInsertIterator, а не на любой элемент в текущей коллекции.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::BackInsertIterator](../cppcx/platform-collections-backinsertiterator-class.md)