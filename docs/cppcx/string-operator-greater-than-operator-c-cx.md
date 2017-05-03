---
title: "Оператор String::operator&gt; (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::operator>"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::operator>"
ms.assetid: d32ad538-b992-4487-a1d3-ad7ba84dbdff
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Оператор String::operator&gt; (C++/CX)
Указывает, является ли значение одного объекта String большим, чем значение второго объекта String.  
  
## Синтаксис  
  
```cpp  
  
bool String::operator>( String^ str1,  
                         String^ str2)  
  
```  
  
#### Параметры  
 `str1`  
 Первый объект String.  
  
 `str2`  
 Второй объект String.  
  
## Возвращаемое значение  
 Значение `true`, если значение `str1` больше `str2`; в противном случае — значение `false`.  
  
## Заметки  
 Этот оператор эквивалентен явному вызову метода [String::CompareOrdinal](../cppcx/string-compareordinal-method.md) и полученный результат больше нуля.  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** vccorlib.h  
  
## См. также  
 [Класс Platform::String](../cppcx/platform-string-class.md)