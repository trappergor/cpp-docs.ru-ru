---
title: "Выражение do-while (C++) | Microsoft Docs"
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
  - "do-while_cpp"
  - "do-while"
  - "do"
  - "while_cpp"
  - "do_cpp"
  - "while"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ключевое слово do [C++]"
  - "ключевое слово do [C++], do-while"
  - "ключевое слово do-while [C++]"
  - "ключевое слово while [C++], do-while"
ms.assetid: e01e6f7c-7da1-4591-87f9-c26ff848e7b0
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Выражение do-while (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Многократно выполняет *оператор*, пока указанное условие завершения \(*выражение*\) не будет равно нулю.  
  
## Синтаксис  
  
```  
  
      do  
   statement  
   while ( expression ) ;  
```  
  
## Заметки  
 Проверка условия завершения выполняется после каждого выполнения цикла; поэтому цикл `do-while` выполняется один или несколько раз, в зависимости от значения выражения завершения.  Выполнение оператора `do-while` может также завершаться, если в теле оператора выполняется оператор [break](../cpp/break-statement-cpp.md), [goto](../cpp/goto-statement-cpp.md) или [return](../Topic/return%20Statement%20\(C++\).md).  
  
 *Выражение* должно иметь арифметический тип или тип указателя.  Выполнение происходит следующим образом:  
  
1.  Выполняется тело оператора.  
  
2.  Затем вычисляется значение *выражения*.  Если значение *выражения* ложно, выполнение оператора `do-while` завершается и управление передается следующему оператору программы.  Если значение *выражения* истинно \(не равно нулю\), процесс повторяется с шага 1.  
  
## Пример  
 В следующем примере показано использование оператора `do-while`:  
  
```  
// do_while_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i = 0;  
    do  
    {  
        printf_s("\n%d",i++);  
    } while (i < 3);  
}  
```  
  
## См. также  
 [Операторы перебора](../cpp/iteration-statements-cpp.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [Оператор while \(C\+\+\)](../cpp/while-statement-cpp.md)   
 [Оператор for \(C\+\+\)](../cpp/for-statement-cpp.md)   
 [Основанное на диапазоне выражение for \(C\+\+\)](../Topic/Range-based%20for%20Statement%20\(C++\).md)