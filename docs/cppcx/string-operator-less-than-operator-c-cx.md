---
title: "Оператор String::operator&lt; (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::operator<"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::operator<"
ms.assetid: 94221597-70dd-4456-a084-5bd2b8fa7723
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Оператор String::operator&lt; (C++/CX)
Указывает, является ли значение одного объекта String меньшим, чем значение второго объекта String.  
  
## Синтаксис  
  
```cpp  
  
bool String::operator<( String^ str1,  
                         String^ str2)  
  
```  
  
#### Параметры  
 `str1`  
 Первый объект String.  
  
 `str2`  
 Второй объект String.  
  
## Возвращаемое значение  
 Значение `true`, если значение `str1` меньше `str2`; в противном случае — значение `false`.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** vccorlib.h  
  
## См. также  
 [Класс Platform::String](../cppcx/platform-string-class.md)