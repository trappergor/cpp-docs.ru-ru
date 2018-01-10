---
title: "Логический оператор или: || | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: '||'
dev_langs: C++
helpviewer_keywords:
- OR operator [C++], logical
- '|| operator'
- OR operator
- logical OR operator
ms.assetid: 31837c99-2655-4bf3-8ded-f13b7a9dc533
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a826b23f94c4eae4a4fdb5379563b015f05dde71
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="logical-or-operator-"></a>Оператор логического ИЛИ: ||
## <a name="syntax"></a>Синтаксис  
  
```  
  
logical-or-expression   
||  
 logical-and-expression  
  
```  
  
## <a name="remarks"></a>Примечания  
 Оператор логического или (`||`) возвращает логическое значение, которое **true** Если один или оба операнда имеют **true** и возвращает **false** в противном случае. Перед вычислением оба операнда неявно преобразуются в тип `bool`; результат также имеет тип `bool`. Логическое ИЛИ имеет ассоциативность в направлении слева направо.  
  
 Операнды оператора логического ИЛИ не обязаны относиться к одному и тому же типу, однако должны иметь целочисленный тип или тип указателя. В качестве операндов часто используются реляционные выражения и выражения равенства.  
  
 В выражении логического ИЛИ сначала полностью вычисляется первый операнд и учитываются все побочные эффекты, и лишь после этого вычисление продолжается.  
  
 Второй операнд вычисляется только в том случае, если первый имеет значение false (0). Это исключает необязательное вычисление второго операнда, если выражение логического ИЛИ имеет значение true.  
  
```  
printf( "%d" , (x == w || x == y || x == z) );  
```  
  
 В приведенном выше примере, если `x` равно `w`, `y` или `z`, то второй аргумент функции `printf` имеет значение true и код выводит значение 1. В противном случае он возвращает значение false и код выводит значение 0. Как только обнаруживается, что одно из значений равно true, вычисление прекращается.  
  
## <a name="operator-keyword-for-124124"></a>Ключевое слово оператора &#124; &#124;  
 **Или** оператор является текстовым эквивалентом `||`. Существует два способа доступа к **или** оператор в программах: включить файл заголовка `iso646.h`, или выполнить компиляцию с [/Za](../build/reference/za-ze-disable-language-extensions.md) параметр компилятора (отключить расширения языка).  
  
## <a name="example"></a>Пример  
  
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
  
## <a name="see-also"></a>См. также  
[Операторы C++ встроенные приоритет и ассоциативность операторов](cpp-built-in-operators-precedence-and-associativity.md) [C++ встроенные операторы, приоритет и ассоциативность операторов](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Логические операторы в C](../c-language/c-logical-operators.md)