---
title: "Оператор while (C++) | Microsoft Docs"
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
  - "while_cpp"
  - "while"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ключевое слово while [C++]"
  - "ключевое слово while [C++], синтаксис"
ms.assetid: 358dbe76-5e5e-4af5-b575-c2293c636899
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор while (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Циклически выполняет *оператор* до тех пор, пока значение параметра *выражение* не будет равно нулю.  
  
## Синтаксис  
  
```  
  
      while ( expression )  
   statement  
```  
  
## Заметки  
 Значение параметра *выражение* проверяется перед каждым выполнением цикла, поэтому цикл `while` выполняется ноль или несколько раз.  Параметр *выражение* должен иметь целочисленный тип, тип указателя или тип класса с однозначным преобразованием в целочисленный тип или тип указателя.  
  
 Выполнение цикла `while` может прекращаться, когда в его теле будет выполнен оператор [break](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md) или [return](../Topic/return%20Statement%20\(C++\).md).  Чтобы прервать текущую итерацию без выхода из цикла `while`, используйте оператор [continue](../cpp/continue-statement-cpp.md).  Оператор **continue** передает управление в следующую итерацию цикла `while`.  
  
 В следующем коде цикл `while` используется для усечения символов подчеркивания в конце строки.  
  
```  
// while_statement.cpp  
  
#include <string.h>  
#include <stdio.h>  
char *trim( char *szSource )  
{  
    char *pszEOS = 0;  
  
    //  Set pointer to character before terminating NULL  
    pszEOS = szSource + strlen( szSource ) - 1;  
  
    //  iterate backwards until non '_' is found   
    while( (pszEOS >= szSource) && (*pszEOS == '_') )  
        *pszEOS-- = '\0';  
  
    return szSource;  
}  
int main()  
{  
    char szbuf[] = "12345_____";  
  
    printf_s("\nBefore trim: %s", szbuf);  
    printf_s("\nAfter trim: %s\n", trim(szbuf));  
}  
```  
  
 Условие завершения вычисляется в начале цикла.  Если символов подчеркивания в конце строки нет, цикл никогда не выполняется.  
  
## См. также  
 [Операторы перебора](../cpp/iteration-statements-cpp.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [Выражение do\-while \(C\+\+\)](../cpp/do-while-statement-cpp.md)   
 [Оператор for \(C\+\+\)](../cpp/for-statement-cpp.md)   
 [Основанное на диапазоне выражение for \(C\+\+\)](../Topic/Range-based%20for%20Statement%20\(C++\).md)