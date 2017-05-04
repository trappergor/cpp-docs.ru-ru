---
title: "Свойство Box::Value | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::Box::Value"
dev_langs: 
  - "C++"
ms.assetid: f456b105-6c14-4737-8c27-ad47d1eabd32
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Свойство Box::Value
Возвращает значение, которое инкапсулируется в объекте `Box`.  
  
## Синтаксис  
  
```cpp  
virtual property T Value{  
   T get();  
}  
```  
  
## Возвращаемое значение  
 Возвращает упакованное значение с тем же типом, который у него был до упаковки.  
  
## Требования  
 **Заголовок:** vccorlib.h  
  
 **Пространство имен:** Platform  
  
## См. также  
 [Класс Platform::Box](../cppcx/platform-box-class.md)   
 [Упаковка](../cppcx/boxing-c-cx.md)