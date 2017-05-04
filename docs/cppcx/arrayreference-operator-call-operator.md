---
title: "Оператор ArrayReference::operator() | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/Platform::ArrayReference::operatorArray^"
dev_langs: 
  - "C++"
ms.assetid: 48726344-82bb-4c1d-b246-ed74b895f99b
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Оператор ArrayReference::operator()
Преобразует текущий объект [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) обратно в класс [Platform::Array](../cppcx/platform-array-class.md).  
  
## Синтаксис  
  
```cpp  
  
Array<__TArg>^ operator ();  
  
```  
  
## Возвращаемое значение  
 Дескриптор для объекта типа `Array<__TArg>^`  
  
## Заметки  
 [Platform::ArrayReference](../cppcx/platform-arrayreference-class.md) и [Platform::Array](../cppcx/platform-array-class.md) являются стандартными шаблонами класса C\+\+, а не ссылочными классами.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  
  
## См. также  
 [Класс Platform::ArrayReference](../cppcx/platform-arrayreference-class.md)