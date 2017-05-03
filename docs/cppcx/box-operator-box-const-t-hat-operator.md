---
title: "Оператор Box::operator Box&lt;const T&gt;^ | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::operator Box<const T>^"
dev_langs: 
  - "C++"
ms.assetid: c43a2e8f-7e9d-4587-960f-1bab48923f82
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Оператор Box::operator Box&lt;const T&gt;^
Позволяет осуществлять преобразования\-упаковки класса значений `const``T` или `enum` класса `T` в `Box<T>`.  
  
## Синтаксис  
  
```cpp  
operator Box<const T>^(const T valueType);  
```  
  
#### Параметры  
 `T`  
 Любой класс значений, структура значений или тип перечисления. Включает встроенные типы в [Пространство имен default](../cppcx/default-namespace.md).  
  
## Возвращаемое значение  
 Экземпляр `Platform::Box<T>``^`, который представляет исходное значение, упакованное в ссылочный класс.  
  
## Требования  
 **Заголовок:** vccorlib.h  
  
 **Пространство имен:** Platform  
  
## См. также  
 [Класс Platform::Box](../cppcx/platform-box-class.md)   
 [Интерфейс Platform::IBox](../cppcx/platform-ibox-interface.md)