---
title: "Метод MapView::First | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView::First"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Метод MapView::First"
ms.assetid: 9d7c7328-4f55-4ea6-a375-9d4e73707b56
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод MapView::First
Возвращает итератор, указывающий первый элемент в представлении сопоставления.  
  
## Синтаксис  
  
```  
  
virtual Windows::Foundation::Collections::IIterator<  
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^   
First();  
```  
  
## Возвращаемое значение  
 Итератор, указывающий первый элемент в представлении сопоставления.  
  
## Заметки  
 Удобный способ сохранения итератора, возвращаемого методом First\(\), — присвоить возвращаемое значение переменной, объявленной с помощью ключевого слова вычитания типа [auto](../Topic/auto%20\(C++\).md). Например, `auto x = myMapView->First();`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::MapView](../cppcx/platform-collections-mapview-class.md)