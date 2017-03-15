---
title: "Оператор дополнения до единицы: ~ | Microsoft Docs"
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
  - "~"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "~ - оператор, синтаксис"
  - "оператор поразрядного дополнения"
  - "compl - оператор"
  - "оператор дополнения до единицы"
  - "тильда (~) - оператор дополнения до единицы"
ms.assetid: 4bf81967-34f7-4b4b-aade-fd03d5da0174
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор дополнения до единицы: ~
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
~ cast-expression  
```  
  
## Заметки  
 Оператор дополнения до единицы \(`~`\), иногда называемый оператором поразрядного отрицания, дополняет свой операнд до единицы в каждом разряде.  То есть каждый бит, равный в операнде 1, в результате становится равным 0,  а каждый бит, равный в операнде 0, в результате становится равным 1.  Операнд оператора дополнения до единицы должен быть целочисленного типа.  
  
## Ключевое слово оператора ~  
 Текстовым эквивалентом оператора `~` является оператор `compl`.  Чтобы получить доступ к оператору `compl` в программах, следует включить файл заголовка `iso646.h` или выполнить компиляцию с параметром компилятора [\/Za](../build/reference/za-ze-disable-language-extensions.md).  
  
## Пример  
  
```  
// expre_One_Complement_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main () {  
   unsigned short y = 0xFFFF;  
   cout << hex << y << endl;  
   y = ~y;   // Take one's complement  
   cout << hex << y << endl;  
}  
```  
  
 В этом примере новое значение, присвоенное переменной `y`, является дополнением до единицы значения 0xFFFF без знака, т. е. значением 0x0000.  
  
 Над целочисленными операндами выполняется восходящее приведение целого типа, и результирующим типом является тип, до которого повышается уровень операнда.  Дополнительные сведения о том, как выполняется такое повышение, см. в разделе [Восходящее приведение целочисленных типов](../misc/integral-promotions.md).  
  
## См. также  
 [Выражения с унарными операторами](../Topic/Expressions%20with%20Unary%20Operators.md)   
 [Операторы C\+\+](../misc/cpp-operators.md)   
 [Операторы C\+\+, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Унарные арифметические операторы](../c-language/unary-arithmetic-operators.md)