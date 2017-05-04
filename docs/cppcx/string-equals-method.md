---
title: "Метод String::Equals | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::Equals"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::Equals"
ms.assetid: b0c78419-242d-4d38-93e3-ff2818412624
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод String::Equals
Указывает, совпадает ли значение заданного объекта String со значением текущего объекта.  
  
## Синтаксис  
  
```cpp  
  
bool String::Equals(Object^ str);  
  
bool String::Equals(String^ str);  
  
```  
  
#### Параметры  
 `str`  
 Объект для сравнения.  
  
## Возвращаемое значение  
 Значение `true`, если `str` равен текущему объекту; в противном случае — значение `false`.  
  
## Заметки  
 Этот метод аналогичен [методу String::CompareOrdinal](../cppcx/string-compareordinal-method.md). В первой перегрузке предполагается, что параметр `str` может быть приведен к объекту String^.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** vccorlib.h  
  
## См. также  
 [Класс Platform::String](../cppcx/platform-string-class.md)