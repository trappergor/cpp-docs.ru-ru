---
title: "Оператор Box::operator T | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::operator T"
dev_langs: 
  - "C++"
ms.assetid: 7445ef5b-563c-4ff0-829d-f22aa558b5ec
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Оператор Box::operator T
Позволяет осуществлять преобразования\-упаковки класса значений `T` или `enum` класса `T` в `Box<T>`.  
  
## Синтаксис  
  
```cpp  
operator Box<T>^(T valueType);  
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