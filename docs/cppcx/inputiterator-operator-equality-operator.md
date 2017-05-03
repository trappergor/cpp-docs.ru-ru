---
title: "InputIterator::operator== - оператор | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::InputIterator::operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InputIterator::operator== - оператор"
ms.assetid: 84f1b69a-77b9-467c-ad1a-2fe8a7c3009e
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# InputIterator::operator== - оператор
Указывает, равен ли текущий объект InputIterator указанному объекту InputIterator.  
  
## Синтаксис  
  
```  
bool operator==(  
   const InputIterator& other  
) const;  
```  
  
#### Параметры  
 `other`  
 Другой объект InputIterator.  
  
## Возвращаемое значение  
 Значение `true`, если текущий объект InputIterator равен объекту `other`, в противном случае — значение `false`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::InputIterator](../cppcx/platform-collections-inputiterator-class.md)