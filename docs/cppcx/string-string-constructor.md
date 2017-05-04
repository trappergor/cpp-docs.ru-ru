---
title: "Конструктор String::String | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::String"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::String"
ms.assetid: 80b6461a-5b12-4dcb-9323-f2c5f310bbc6
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Конструктор String::String
Инициализирует новый экземпляр класса String с копией входных данных строки.  
  
## Синтаксис  
  
```cpp  
  
String();  
  
String(  
  char16* s  
)  
  
String(  
  char16* s,   
  unsigned int n  
)  
```  
  
## Параметры  
 `s`  
 Серия расширенных символов, инициализирующих строку.  char16  
  
 `n`  
 Число, указывающее длину строки.  
  
## Заметки  
 Если производительность имеет решающее значение, и вы управляете временем жизни строки исходного кода, можно использовать [Platform::StringReference](../cppcx/platform-stringreference-class.md) вместо String.  
  
## Пример  
  
```  
String^ s = L”Hello!”;  
```  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** vccorlib.h  
  
## См. также  
 [Класс Platform::String](../cppcx/platform-string-class.md)