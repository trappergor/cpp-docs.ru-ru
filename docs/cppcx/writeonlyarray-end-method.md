---
title: "WriteOnlyArray::end - метод | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::WriteOnlyArray::end"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WriteOnlyArray::end - метод"
ms.assetid: 045045fe-f210-400b-b688-7abb95fc702a
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WriteOnlyArray::end - метод
Возвращает указатель на элемент, следующий за последним элементом в массиве.  
  
## Синтаксис  
  
```cpp  
T* end() const;  
```  
  
## Возвращаемое значение  
 Итератор указателя на элемент, следующий за последним элементом в массиве.  
  
## Заметки  
 Этот итератор можно использовать с алгоритмами STL для выполнения операций, таких как `std::sort`, в элементах массива.  
  
## Требования  
 **Заголовок:** vccorlib.h  
  
 **Пространство имен:** Platform  
  
## См. также  
 [Класс Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md)   
 [Классы Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)