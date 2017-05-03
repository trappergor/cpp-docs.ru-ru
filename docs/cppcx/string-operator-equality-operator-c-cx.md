---
title: "Оператор String::operator== (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::operator=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::operator=="
ms.assetid: c804b269-64f9-4bc0-929b-2dfa87bf46ac
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Оператор String::operator== (C++/CX)
Указывает, равны ли текстовые значения двух указанных объектов String.  
  
## Синтаксис  
  
```cpp  
  
bool String::operator==( String^ str1,  
                         String^ str2)  
  
```  
  
#### Параметры  
 `str1`  
 Первый из сравниваемых объектов String.  
  
 `str2`  
 Второй из сравниваемых объектов String.  
  
## Возвращаемое значение  
 Значение `true`, если значения параметров `str1` и `str2` равны; в противном случае — значение `false`.  
  
## Заметки  
 Этот оператор аналогичен [методу String::CompareOrdinal](../cppcx/string-compareordinal-method.md).  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** vccorlib.h  
  
## См. также  
 [Класс Platform::String](../cppcx/platform-string-class.md)