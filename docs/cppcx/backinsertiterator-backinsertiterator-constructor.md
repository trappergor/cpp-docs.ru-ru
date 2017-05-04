---
title: "Конструктор BackInsertIterator::BackInsertIterator | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::BackInsertIterator::BackInsertIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Конструктор BackInsertIterator::BackInsertIterator"
ms.assetid: ae6f0213-a7bb-43b8-9a5e-7a8dad7c76f8
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Конструктор BackInsertIterator::BackInsertIterator
Инициализирует новый экземпляр класса `BackInsertIterator`.  
  
## Синтаксис  
  
```  
  
explicit BackInsertIterator(  
   Windows::Foundation::Collections::IVector<T>^ v  
);  
```  
  
#### Параметры  
 `v`  
 Объект IVector\<T\>.  
  
## Заметки  
 `BackInsertIterator` вставляет элементы после последнего элемента объекта, указанного параметром `v`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::BackInsertIterator](../cppcx/platform-collections-backinsertiterator-class.md)