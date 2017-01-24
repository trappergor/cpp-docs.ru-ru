---
title: "__int8, __int16, __int32, __int64 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__int8_cpp"
  - "__int64"
  - "__int8"
  - "__int16"
  - "__int16_cpp"
  - "__int64_cpp"
  - "__int32_cpp"
  - "__int32"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__int16 - ключевое слово [C++]"
  - "__int32 - ключевое слово [C++]"
  - "__int64 - ключевое слово [C++]"
  - "__int8 - ключевое слово [C++]"
  - "integer - тип данных, целочисленные типы в C++"
  - "целочисленные типы [C++]"
ms.assetid: 8e384602-2578-4980-8cc8-da63842356b2
caps.latest.revision: 11
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __int8, __int16, __int32, __int64
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Блок, относящийся только к системам Microsoft  
 В Microsoft C\/C\+\+ поддерживаются целочисленные типы с указанием размера.  Это позволяет объявлять 8\-, 16\-, 32\- и 64\-разрядные целочисленные переменные при помощи спецификатора типа **\_\_int***n* \(где *n* имеет значение 8, 16, 32 или 64\).  
  
 В следующем примере объявляется по одной переменной каждого из этих целочисленных типов с указанием размера:  
  
```  
__int8 nSmall;      // Declares 8-bit integer  
__int16 nMedium;    // Declares 16-bit integer  
__int32 nLarge;     // Declares 32-bit integer  
__int64 nHuge;      // Declares 64-bit integer  
```  
  
 Типы `__int8`, `__int16` и `__int32` аналогичны типам данных ANSI с таким же размером. Они могут использоваться для написания переносимого кода, который одинаково работает на разных платформах.  Тип данных `__int8` аналогичен типу `char`, тип `__int16` — типу **short**, а тип `__int32` — типу `int`.  Тип `__int64` не имеет эквивалента в ANSI.  
  
## Пример  
 В следующем примере показано, каким образом параметр \_\_int*xx* будет повышен до уровня `int`:  
  
```  
// sized_int_types.cpp  
  
#include <stdio.h>  
  
void func(int i) {  
    printf_s("%s\n", __FUNCTION__);  
}  
  
int main()  
{  
    __int8 i8 = 100;  
    func(i8);   // no void func(__int8 i8) function  
                // __int8 will be promoted to int  
}  
```  
  
  **func**   
## Завершение блока, относящегося только к системам Майкрософт  
  
## См. также  
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [Фундаментальные типы](../cpp/fundamental-types-cpp.md)   
 [Диапазоны типов данных](../cpp/data-type-ranges.md)