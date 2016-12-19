---
title: "Битовый оператор ИЛИ (включительно): | | Microsoft Docs"
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
  - "bitor"
  - "|"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "| - оператор"
  - "побитовые операторы, OR - оператор"
  - "включающий оператор OR"
  - "OR - оператор, побитовое включающее"
ms.assetid: 4c8a6a68-d828-447d-875a-aedb4ce3aa9a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Битовый оператор ИЛИ (включительно): |
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
expression   
|  
 expression  
  
```  
  
## Заметки  
 Оператор побитового ИЛИ \(         **&#124;** \) сравнивает каждый бит первого операнда с соответствующим битом второго операнда.  Если любой из битов равен единице, соответствующий бит результата устанавливается равным единице, а  в противном случае — нулю.  
  
 Оба операнда оператора побитового ИЛИ должны быть целочисленного типа.  К операндам применяются обычные арифметические преобразования, описанные в разделе [Арифметические преобразования](../misc/arithmetic-conversions.md).  
  
## Ключевое слово оператора &#124;  
 Оператор `bitor` является текстовым эквивалентом оператора              **&#124;** .  Чтобы получить доступ к оператору `bitor` в программах, следует включить файл заголовка `iso646.h` или выполнить компиляцию с параметром компилятора [\/Za](../build/reference/za-ze-disable-language-extensions.md) \("Отключить расширения языка"\).  
  
## Пример  
  
```  
// expre_Bitwise_Inclusive_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise inclusive OR  
#include <iostream>  
using namespace std;  
  
int main() {  
   unsigned short a = 0x5555;      // pattern 0101 ...  
   unsigned short b = 0xAAAA;      // pattern 1010 ...  
  
   cout  << hex << ( a | b ) << endl;   // prints "ffff" pattern 1111 ...  
}  
```  
  
## См. также  
 [Побитовые операторы в C\+\+](../Topic/C++%20Bitwise%20Operators.md)   
 [Операторы C\+\+](../misc/cpp-operators.md)   
 [Операторы C\+\+, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Побитовые операторы в C](../c-language/c-bitwise-operators.md)