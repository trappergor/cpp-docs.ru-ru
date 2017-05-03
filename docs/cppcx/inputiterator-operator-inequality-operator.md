---
title: "InputIterator::operator!= - оператор | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::InputIterator::operator!="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InputIterator::operator!= - оператор"
ms.assetid: 68a33a74-4bf9-4c91-858e-9c621861b81e
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# InputIterator::operator!= - оператор
Указывает, отличен ли текущий объект InputIterator от указанного объекта InputIterator.  
  
## Синтаксис  
  
```  
bool operator!=(  
   const InputIterator& other  
) const;  
```  
  
#### Параметры  
 `other`  
 Другой объект InputIterator.  
  
## Возвращаемое значение  
 Значение `true`, если текущий объект InputIterator не равен объекту `other`, в противном случае — значение `false`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::InputIterator](../cppcx/platform-collections-inputiterator-class.md)