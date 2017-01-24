---
title: "Оператор логического отрицания: ! | Microsoft Docs"
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
  - "!"
  - "Not"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "! оператор"
  - "логическое отрицание"
  - "NOT - оператор"
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор логического отрицания: !
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
! cast-expression  
```  
  
## Заметки  
 Оператор логического отрицания \(**\!**\) меняет значение своего операнда на противоположное.  Операнд должен иметь арифметический тип или тип указателя \(либо выражение, результатом которого является арифметический тип или тип указателя\).  Операнд неявно преобразуется в тип `bool`.  Результат — **true**, если преобразованный операнд — **false**; результат — **false**, если преобразованный операнд — **true**.  Результат имеет тип `bool`.  
  
 Для выражения *e* унарное выражение **\!***e* эквивалентно выражению **\(***e* `==` 0\), за исключением случаев, когда используются перегруженные операторы.  
  
## Ключевое слово оператора для \!  
 Оператор **not** является текстовым эквивалентом **\!**.  Чтобы получить доступ к оператору **not** в программах, следует включить файл заголовка `iso646.h` или выполнить компиляцию с параметром компилятора [\/Za](../build/reference/za-ze-disable-language-extensions.md) \("Отключить расширения языка"\).  
  
## Пример  
  
```  
// expre_Logical_NOT_Operator.cpp  
// compile with: /EHsc  
#include <iostream>  
using namespace std;  
  
int main() {  
   int i = 0;  
   if (!i)  
      cout << "i is zero" << endl;  
}  
```  
  
## См. также  
 [Выражения с унарными операторами](../Topic/Expressions%20with%20Unary%20Operators.md)   
 [Операторы C\+\+](../misc/cpp-operators.md)   
 [Операторы C\+\+, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Унарные арифметические операторы](../c-language/unary-arithmetic-operators.md)