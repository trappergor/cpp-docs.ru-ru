---
title: "Свойство WriteOnlyArray::FastPass | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::WriteOnlyArray::FastPass"
dev_langs: 
  - "C++"
ms.assetid: f7a54ae0-afa0-4728-8736-c63933f789aa
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Свойство WriteOnlyArray::FastPass
Указывает, можно ли выполнить внутреннюю оптимизацию FastPass. Не предназначен для использования в пользовательском коде.  
  
## Синтаксис  
  
```cpp  
property bool FastPass{  
   bool get() const;  
}  
```  
  
## Возвращаемое значение  
 Логическое значение, указывающее, является ли массив FastPass.  
  
## Требования  
 **Заголовок:** vccorlib.h  
  
 **Пространство имен:** Platform  
  
## См. также  
 [Класс Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md)