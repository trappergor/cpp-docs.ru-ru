---
title: "Оператор Box::operator Box&lt;volatile T&gt;^ | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::operator Box<volatile T>^"
dev_langs: 
  - "C++"
ms.assetid: 90fffbf6-3429-46d0-bfaf-d99b7f48de6f
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Оператор Box::operator Box&lt;volatile T&gt;^
Позволяет осуществлять преобразования\-упаковки из класса значений `volatile``T` или `enum` типа `T` в `Box<T>`.  
  
## Синтаксис  
  
```cpp  
operator Box<volatile T>^(volatile T valueType);  
```  
  
#### Параметры  
 `T`  
 Любой тип перечисления, класс значений или структура значений. Включает встроенные типы в [Пространство имен default](../cppcx/default-namespace.md).  
  
## Возвращаемое значение  
 Экземпляр `Platform::Box<T>``^`, который представляет исходное значение, упакованное в ссылочный класс.  
  
## Требования  
 **Заголовок:** vccorlib.h  
  
 **Пространство имен:** Platform  
  
## См. также  
 [Класс Platform::Box](../cppcx/platform-box-class.md)   
 [Интерфейс Platform::IBox](../cppcx/platform-ibox-interface.md)   
 [Упаковка](../cppcx/boxing-c-cx.md)