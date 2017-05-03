---
title: "Метод String::Length | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::Length"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::Length"
ms.assetid: 92376897-1bf2-4b7a-9298-d2d3f05d8d6b
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод String::Length
Получает количество символов в указанном объекте String.  
  
## Синтаксис  
  
```cpp  
  
unsigned int Length()  
```  
  
## Возвращаемое значение  
 Количество символов в указанном объекте String.  
  
## Заметки  
 Длина объекта String без символов равна нулю. Длина следующего объекта String равна 5.  
  
```  
  
String^ str = "Hello";  
int len = str->Length(); //len = 5  
```  
  
 Массив символов, возвращаемый [Метод String::Data](../cppcx/string-data-method.md), имеет один дополнительный символ — завершающий NULL или "\\0". Этот символ также имеет длину 2 байта.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** vccorlib.h  
  
## См. также  
 [Класс Platform::String](../cppcx/platform-string-class.md)