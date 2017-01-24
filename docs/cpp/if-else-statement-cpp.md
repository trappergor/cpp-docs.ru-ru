---
title: "Оператор if-else (C++) | Microsoft Docs"
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
  - "else_cpp"
  - "else"
  - "if_cpp"
  - "if"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "else - ключевое слово [C++]"
  - "if - ключевое слово [C++]"
  - "if - ключевое слово [C++], if-else"
ms.assetid: f8c45cde-6bce-42ae-81db-426b3dbd4caa
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор if-else (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Управляет условным ветвлением.  
  
## Синтаксис  
  
```  
  
      if ( expression )  
   statement1  
[else  
   statement2]  
```  
  
## Заметки  
 Если значение параметра *выражение* не равно нулю, то *выражение1* выполняется.  Если имеется необязательный оператор **else**, то параметр *выражение2* выполняется, если значение параметра *выражение* равно нулю.  *Выражение* должно иметь арифметический тип или тип указателя, либо оно должно быть типом класса, который определяет однозначное преобразование в арифметический тип или тип указателя. \(Дополнительные сведения о преобразованиях см. в разделе [Стандартные преобразования](../cpp/standard-conversions.md).\)  
  
 В обеих формах оператора **if** вычисляется параметр *выражение* \(который может иметь любое значение, за исключением структуры\), включая все побочные эффекты.  Управление от оператора **if** передается следующему оператору в программе, кроме случаев, когда в параметре *выражение* содержится оператор [break](../cpp/break-statement-cpp.md), [continue](../cpp/continue-statement-cpp.md) или [goto](../cpp/goto-statement-cpp.md).  
  
 Условие **else** в операторе `if...else` связывается с ближайшим предыдущим **if** в той же области видимости, для которого нет соответствующего условия **else**.  
  
 Для того чтобы следующий пример не содержал противоречий касательно пар `if...else`, необходимо убрать комментарии перед фигурными скобками.  
  
## Пример  
  
```  
// if_else_statement.cpp  
#include <stdio.h>  
  
int main()   
{  
   int x = 0;  
   if (x == 0)  
   {  
      printf_s("x is 0!\n");  
   }  
   else  
   {  
      printf_s("x is not 0!\n"); // this statement will not be executed  
   }  
  
   x = 1;  
   if (x == 0)  
   {  
      printf_s("x is 0!\n"); // this statement will not be executed  
   }  
   else  
   {  
      printf_s("x is not 0!\n");  
   }  
  
   return 0;  
}  
```  
  
  **x is 0\!**  
**x is not 0\!**   
## См. также  
 [Инструкции выбора](../cpp/selection-statements-cpp.md)   
 [Ключевые слова в C\+\+](../cpp/keywords-cpp.md)   
 [Оператор switch \(C\+\+\)](../cpp/switch-statement-cpp.md)