---
title: "Операторы равенства: == и != | Microsoft Docs"
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
  - "not_eq"
  - "!="
  - "=="
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "!= - оператор"
  - "== - оператор"
  - "оператор "равно""
  - "оператор равенства"
  - "оператор равенства, синтаксис"
  - "оператор сравнения "не равно""
  - "not_eq - оператор"
ms.assetid: ba4e9659-2392-4fb4-be5a-910a2a6df45a
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Операторы равенства: == и !=
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Синтаксис  
  
```  
  
      expression == expression  
expression != expression  
```  
  
## Заметки  
 Бинарные операторы равенства сравнивают операнды для строгого равенства или неравенства.  
  
 Операторы равенства, то есть равно \(`==`\) и не равно \(`!=`\), имеют более низкий приоритет, чем операторы отношения, но их поведение аналогично.  Результат этих операторов будет принадлежать типу `bool`.  
  
 Оператор "равно" \(`==`\) возвращает значение **true** \(1\), если оба операнда имеют одинаковые значения; в противном случае он возвращает значение **false** \(0\).  Оператор "не равно" \(`!=`\) возвращает значение **true**, если операнды имеют неравные значения; в противном случае он возвращает значение **false**.  
  
## Ключевое слово оператора \!\=  
 Текстовым эквивалентом оператора `!=` является оператор `not_eq`.  Чтобы получить доступ к оператору `not_eq` в программах, следует включить файл заголовка `iso646.h` или выполнить компиляцию с параметром компилятора [\/Za](../build/reference/za-ze-disable-language-extensions.md) \("Отключить расширения языка"\).  
  
## Пример  
  
```  
// expre_Equality_Operators.cpp  
// compile with: /EHsc  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   cout  << boolalpha  
         << "The true expression 3 != 2 yields: "  
         << (3 != 2) << endl  
         << "The false expression 20 == 10 yields: "  
         << (20 == 10) << endl;  
}  
```  
  
 Операторы равенства могут сравнивать указатели на члены одного типа.  При таком сравнении выполняются преобразования указателей на члены, как описано в разделе [Преобразования указателей на члены](../misc/pointer-to-member-conversions.md).  Указатели на члены также можно сравнить с константным выражением, результатом которого является значение 0.  
  
## См. также  
 [Выражения с бинарными операторами](../cpp/expressions-with-binary-operators.md)   
 [Операторы C\+\+](../misc/cpp-operators.md)   
 [Операторы C\+\+, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Операторы отношения и равенства C](../c-language/c-relational-and-equality-operators.md)