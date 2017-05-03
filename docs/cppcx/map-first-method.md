---
title: "Метод Map::First | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map::First"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Метод Map::First"
ms.assetid: bb1a4458-ecc3-43b0-b808-1693f853ad82
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод Map::First
Возвращает итератор, указывающий первый элемент в сопоставлении или `nullptr`, если сопоставление пусто.  
  
## Синтаксис  
  
```  
  
virtual Windows::Foundation::Collections::IIterator<  
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();  
```  
  
## Возвращаемое значение  
 Итератор, указывающий первый элемент на карте.  
  
## Заметки  
 Удобный способ сохранения итератора, возвращаемого методом First\(\), — присвоить возвращаемое значение переменной, объявленной с помощью ключевого слова вычитания типа [auto](../Topic/auto%20\(C++\).md). Например, `auto x = myMap->First();`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::Map](../cppcx/platform-collections-map-class.md)   
 [Коллекции \(C\+\+\/CX\)](../cppcx/collections-c-cx.md)