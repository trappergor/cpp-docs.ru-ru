---
title: "WriteOnlyArray::begin - метод | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::WriteOnlyArray::begin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WriteOnlyArray::begin - метод"
ms.assetid: 25025fa0-8f55-4abf-93ad-71db45ddfae3
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WriteOnlyArray::begin - метод
Возвращает указатель на первый элемент массива.  
  
## Синтаксис  
  
```cpp  
T* begin() const;  
```  
  
## Возвращаемое значение  
 Указатель на первый элемент массива.  
  
## Заметки  
 Этот итератор можно использовать с алгоритмами STL, такими как `std::sort`, для выполнения действий с элементами в массиве.  
  
## Требования  
 **Заголовок:** vccorlib.h  
  
 **Пространство имен:** Platform  
  
## См. также  
 [Класс Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md)   
 [Классы Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)