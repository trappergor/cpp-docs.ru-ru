---
title: "Битовый оператор ИЛИ (исключительное): ^ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "^ - оператор"
  - "побитовые операторы, OR - оператор"
  - "исключающий оператор OR"
  - "операторы [C++], побитовые"
  - "операторы [C++], логический"
  - "OR - оператор, побитовое исключающее"
  - "XOR - оператор"
ms.assetid: f9185d85-65d5-4f64-a6d6-679758d52217
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Битовый оператор ИЛИ (исключительное): ^
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
expression ^ expression  
```  
  
## Заметки  
 Оператор побитового эксклюзивного ИЛИ \(**^**\) сравнивает каждый бит первого операнда с соответствующим битом второго операнда.  Если один бит равен 0, а другой равен 1, соответствующий бит результата устанавливается равным 1.  в противном случае — нулю.  
  
 Оба операнда оператора побитового эксклюзивного ИЛИ должны быть целочисленного типа.  К операндам применяются обычные арифметические преобразования, описанные в разделе [Арифметические преобразования](../misc/arithmetic-conversions.md).  
  
## Ключевое слово оператора ^  
 Оператор **xor** является текстовым эквивалентом **^**.  Чтобы получить доступ к оператору **xor** в программах, следует включить файл заголовка `iso646.h` или выполнить компиляцию с параметром компилятора [\/Za](../build/reference/za-ze-disable-language-extensions.md) \("Отключить расширения языка"\).  
  
## Пример  
  
```  
// expre_Bitwise_Exclusive_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate bitwise exclusive OR  
#include <iostream>  
using namespace std;  
int main() {  
   unsigned short a = 0x5555;      // pattern 0101 ...  
   unsigned short b = 0xFFFF;      // pattern 1111 ...  
  
   cout  << hex << ( a ^ b ) << endl;   // prints "aaaa" pattern 1010 ...  
}  
```  
  
## См. также  
 [Побитовые операторы в C\+\+](../Topic/C++%20Bitwise%20Operators.md)   
 [Операторы C\+\+](../misc/cpp-operators.md)   
 [Операторы C\+\+, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Побитовые операторы в C](../c-language/c-bitwise-operators.md)