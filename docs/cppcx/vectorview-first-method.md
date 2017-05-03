---
title: "VectorView::First - метод | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::First"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::First - метод"
ms.assetid: 543a5c5b-8ce3-4be3-9fad-726928de7855
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::First - метод
Возвращает итератор, указывающий первый элемент объекта VectorView.  
  
## Синтаксис  
  
```  
  
virtual Windows::Foundation::Collections::IIterator<T>^   
   First();  
```  
  
## Возвращаемое значение  
 Итератор, указывающий первый элемент объекта VectorView.  
  
## Заметки  
 Удобный способ сохранения итератора, возвращаемого методом First\(\), — присвоить возвращаемое значение переменной, объявленной с помощью ключевого слова вычитания типа [auto](../Topic/auto%20\(C++\).md). Например, `auto x = myVectorView->First();`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [VectorView Class](http://msdn.microsoft.com/ru-ru/79697692-ae58-40e0-958f-cf1be6347994)