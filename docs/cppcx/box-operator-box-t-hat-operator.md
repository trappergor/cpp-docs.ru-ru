---
title: "Оператор Box::operator Box&lt;T&gt;^ | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::operator Box<T>^"
dev_langs: 
  - "C++"
ms.assetid: c2c89385-c334-4b09-8f87-d46ea4809232
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Оператор Box::operator Box&lt;T&gt;^
Позволяет осуществлять преобразования\-упаковки класса значений `T` в `Box<T>`.  
  
## Синтаксис  
  
```cpp  
operator Box<const T>^(const T valueType);  
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