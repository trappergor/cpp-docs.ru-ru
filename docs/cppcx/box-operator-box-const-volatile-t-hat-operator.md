---
title: "Оператор Box::operator Box&lt;const volatile T&gt;^ | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::operator Box<const volatile T>^"
dev_langs: 
  - "C++"
ms.assetid: 3c91cf0f-1e90-4daf-8468-a7d8aedb6784
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Оператор Box::operator Box&lt;const volatile T&gt;^
Позволяет осуществлять преобразования\-упаковки из класса значений `const volatile``T` или `enum` типа `T` в `Box<T>`.  
  
## Синтаксис  
  
```cpp  
operator Box<const volatile T>^(const volatile T valueType);  
```  
  
#### Параметры  
 `T`  
 Любой тип перечисления, класс значений или структура значений. Включает встроенные типы в [Пространство имен default](../cppcx/default-namespace.md).  
  
## Возвращаемое значение  
 Экземпляр `Platform::Box<T>``^`, который представляет исходное значение, упакованное в класс ссылки.  
  
## Требования  
 **Заголовок:** vccorlib.h  
  
 **Пространство имен:** Platform  
  
## См. также  
 [Класс Platform::Box](../cppcx/platform-box-class.md)   
 [Интерфейс Platform::IBox](../cppcx/platform-ibox-interface.md)   
 [Упаковка](../cppcx/boxing-c-cx.md)