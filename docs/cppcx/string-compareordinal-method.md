---
title: "Метод String::CompareOrdinal | Microsoft Docs"
ms.custom: ""
ms.date: "02/09/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform/Platform::String::CompareOrdinal"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Platform::String::CompareOrdinal"
ms.assetid: dd4a7acc-fd23-4f1e-af85-64b9086f63f8
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод String::CompareOrdinal
Сравнивает два объекта `String`, оценивая числовые значения соответствующих символов в двух строковых значениях, представленных объектами.  
  
## Синтаксис  
  
```cpp  
  
int CompareOrdinal(  
           String^ str1,   
           String^ str2)  
  
```  
  
#### Параметры  
 `str1`  
 Первый объект String.  
  
 `str2`  
 Второй объект String.  
  
## Возвращаемое значение  
 Целое число, выражающее лексическое соотношение двух сравниваемых значений. В следующей таблице перечислены возможные возвращаемые значения.  
  
|Значение|Условие|  
|--------------|-------------|  
|\-1|Значение `str1` меньше `str2`.|  
|0|Значение `str1` равно значению `str2`.|  
|1|Значение `str1` больше значения `str2`.|  
  
## Требования  
 **Минимальный поддерживаемый клиент:** [!INCLUDE[win8](../cppcx/includes/win8-md.md)]  
  
 **Минимальный поддерживаемый сервер:** [!INCLUDE[winserver8](../cppcx/includes/winserver8-md.md)]  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** vccorlib.h  
  
## См. также  
 [Класс Platform::String](../cppcx/platform-string-class.md)