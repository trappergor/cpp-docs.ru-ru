---
title: "WriteOnlyArray::set - функция | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::WriteOnlyArray::set"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "WriteOnlyArray::set - функция"
ms.assetid: 0359f922-f25e-47d1-b7df-87e7fd0f76e5
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WriteOnlyArray::set - функция
Задает указанное значение по заданному индексу массива.  
  
## Синтаксис  
  
```cpp  
T& set(  
   unsigned int indexArg,  
   T valueArg);  
```  
  
#### Параметры  
 `indexArg`  
 Задаваемый индекс элемента.  
  
 `valueArg`  
 Задаваемое в `indexArg` значение.  
  
## Возвращаемое значение  
 Ссылка на элемент, который только что был установлен.  
  
## Требования  
 **Заголовок:** vccorlib.h  
  
 **Пространство имен:** Platform  
  
## См. также  
 [Класс Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md)   
 [Классы Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)