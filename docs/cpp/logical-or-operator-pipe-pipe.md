---
title: "Оператор логического ИЛИ: || | Microsoft Docs"
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
  - "||"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "|| - оператор"
  - "логический оператор OR (||)"
  - "OR - оператор"
  - "OR - оператор, логический"
ms.assetid: 31837c99-2655-4bf3-8ded-f13b7a9dc533
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Оператор логического ИЛИ: ||
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
logical-or-expression   
||  
 logical-and-expression  
  
```  
  
## Заметки  
 Оператор логического ИЛИ \(`||`\) возвращает логическое значение **true**, если один или оба операнда имеют значение **true**; в противном случае он возвращает значение **false**.  Перед вычислением оба операнда неявно преобразуются в тип `bool`; результат также имеет тип `bool`.  Логическое ИЛИ имеет ассоциативность в направлении слева направо.  
  
 Операнды оператора логического ИЛИ не обязаны относиться к одному и тому же типу, однако должны иметь целочисленный тип или тип указателя.  В качестве операндов часто используются реляционные выражения и выражения равенства.  
  
 В выражении логического ИЛИ сначала полностью вычисляется первый операнд и учитываются все побочные эффекты, и лишь после этого вычисление продолжается.  
  
 Второй операнд вычисляется только в том случае, если первый имеет значение false \(0\).  Это исключает необязательное вычисление второго операнда, если выражение логического ИЛИ имеет значение true.  
  
```  
printf( "%d" , (x == w || x == y || x == z) );  
```  
  
 В приведенном выше примере, если `x` равно `w`, `y` или `z`, то второй аргумент функции `printf` имеет значение true и код выводит значение 1.  В противном случае он возвращает значение false и код выводит значение 0.  Как только обнаруживается, что одно из значений равно true, вычисление прекращается.  
  
## Ключевое слово оператора &#124;&#124;  
 Текстовым эквивалентом оператора `||` является оператор **or**.  Сделать оператор **or** доступным в ваших программах можно двумя способами: включить файл заголовка `iso646.h` или установить параметр компиляции [\/Za](../build/reference/za-ze-disable-language-extensions.md) \(отключить расширения языка\).  
  
## Пример  
  
```  
// expre_Logical_OR_Operator.cpp  
// compile with: /EHsc  
// Demonstrate logical OR  
#include <iostream>  
using namespace std;  
int main() {  
   int a = 5, b = 10, c = 15;  
   cout  << boolalpha  
         << "The true expression "  
         << "a < b || b > c yields "  
         << (a < b || b > c) << endl  
         << "The false expression "  
         << "a > b || b > c yields "  
         << (a > b || b > c) << endl;  
}  
```  
  
## См. также  
 [Логические операторы](../misc/logical-operators.md)   
 [Операторы C\+\+](../misc/cpp-operators.md)   
 [Операторы C\+\+, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Логические операторы в C](../c-language/c-logical-operators.md)