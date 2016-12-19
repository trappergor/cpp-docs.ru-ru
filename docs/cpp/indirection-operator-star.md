---
title: "Оператор косвенного обращения: * | Microsoft Docs"
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
  - "* - оператор"
  - "оператор косвенного обращения"
  - "оператор косвенного обращения, синтаксис"
  - "операторы [C++], косвенное обращение"
ms.assetid: c50309e1-6c02-4184-9fcb-2e13c1f4ac03
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор косвенного обращения: *
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
* cast-expression  
```  
  
## Заметки  
 Унарный косвенный оператор \(**\***\) разыменует указатель, то есть преобразует значение указателя в l\-значение.  Операнд косвенного оператора должен быть указателем на тип.  Результат косвенного выражения — тип, производным которого является тип указателя.  Использование оператора **\*** в этом контексте отличается от его значения как бинарного оператора, то есть умножения.  
  
 Если операнд указывает на функцию, результатом является указатель функции.  Если он указывает на место хранения, результатом является l\-значение, указывающее на место хранения.  
  
 Косвенный оператор может использоваться кумулятивно для разыменования указателей на указатели.  Например:  
  
```  
// expre_Indirection_Operator.cpp  
// compile with: /EHsc  
// Demonstrate indirection operator  
#include <iostream>  
using namespace std;  
int main() {  
   int n = 5;  
   int *pn = &n;  
   int **ppn = &pn;  
  
   cout  << "Value of n:\n"  
         << "direct value: " << n << endl  
         << "indirect value: " << *pn << endl  
         << "doubly indirect value: " << **ppn << endl  
         << "address of n: " << pn << endl  
         << "address of n via indirection: " << *ppn << endl;  
}  
```  
  
 Если значение указателя недопустимо, результат становится неопределенным.  Ниже приведены наиболее распространенные условия, при которых значение указателя становится недопустимым.  
  
-   Указатель является пустым указателем.  
  
-   Указатель определяет адрес локального элемента, не видимого во время обращения.  
  
-   Указатель определяет адрес, выравнивание которого не подходит для типа указываемого объекта.  
  
-   Указатель определяет адрес, который не используется выполняемой программой.  
  
## См. также  
 [Выражения с унарными операторами](../Topic/Expressions%20with%20Unary%20Operators.md)   
 [Операторы C\+\+](../misc/cpp-operators.md)   
 [Операторы C\+\+, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Оператор address\-of: &](../cpp/address-of-operator-amp.md)   
 [Операторы косвенного обращения и адреса операнда](../c-language/indirection-and-address-of-operators.md)