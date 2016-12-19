---
title: "Оператор побитового И: &amp; | Microsoft Docs"
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
  - "bitand"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "& - оператор, побитовые операторы"
  - "AND - оператор"
  - "побитовые операторы, AND - оператор"
ms.assetid: 76f40de3-c417-47b9-8a77-532f3fc990a5
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор побитового И: &amp;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
expression   
&  
 expression  
  
```  
  
## Заметки  
 Выражения могут представлять собой другие and\-выражения или \(в зависимости от упомянутых ниже типов ограничений\) выражения равенства, выражения связей, выражения сложения, выражения умножения, выражения указателя на член, выражения приведения, унарные выражения, постфиксные выражения или основные выражения.  
  
 Оператор побитового И \(**&**\) сравнивает каждый бит первого операнда с соответствующим битом второго операнда.  Если оба бита равны 1, соответствующий бит результата устанавливается равным единице.  в противном случае — нулю.  
  
 Оба операнда оператора побитового И должны иметь целочисленный тип.  К операндам применяются обычные арифметические преобразования, описанные в разделе [Арифметические преобразования](../misc/arithmetic-conversions.md).  
  
## Ключевое слово оператора &  
 Текстовым эквивалентом оператора **&** является оператор `bitand`.  Чтобы получить доступ к оператору `bitand` в программах, следует включить файл заголовка `iso646.h` или выполнить компиляцию с параметром компилятора [\/Za](../build/reference/za-ze-disable-language-extensions.md) \("Отключить расширения языка"\).  
  
## Пример  
  
```  
// expre_Bitwise_AND_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise AND  
#include <iostream>  
using namespace std;  
int main() {  
   unsigned short a = 0xFFFF;      // pattern 1111 ...  
   unsigned short b = 0xAAAA;      // pattern 1010 ...  
  
   cout  << hex << ( a & b ) << endl;   // prints "aaaa", pattern 1010 ...  
}  
```  
  
## См. также  
 [Побитовые операторы в C\+\+](../Topic/C++%20Bitwise%20Operators.md)   
 [Операторы C\+\+](../misc/cpp-operators.md)   
 [Операторы C\+\+, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Побитовые операторы в C](../c-language/c-bitwise-operators.md)