---
title: 'Оператор логического и: &amp; &amp; | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- '&&'
dev_langs:
- C++
helpviewer_keywords:
- logical AND operator
- AND operator
- '&& operator'
ms.assetid: 50cfa664-a8c4-4b31-9bab-2f80d7cd2d1f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f683b7ff17a1dd3945f5cb554a7440ab47fad454
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="logical-and-operator-ampamp"></a>Оператор логического и: &amp;&amp;
## <a name="syntax"></a>Синтаксис  
  
```  
  
expression   
&&  
 expression  
  
```  
  
## <a name="remarks"></a>Примечания  
 Логический оператор AND (**&&**) возвращает логическое значение, которое **true** Если оба операнда имеют **true** и возвращает **false** в противном случае. Перед вычислением оба операнда неявно преобразуются в тип `bool`; результат также имеет тип `bool`. Логическое И имеет ассоциативность в направлении слева направо.  
  
 Операнды оператора логического И не должны быть одинакового типа, но должны быть целочисленного типа или типа указателя. В качестве операндов часто используются реляционные выражения и выражения равенства.  
  
 Перед продолжением вычисления выражения логического И полностью вычисляется первый операнд и учитываются все побочные эффекты.  
  
 Второй операнд вычисляется только в том случае, если результат вычисления первого операнда — значение true (не нуль). Такое вычисление исключает необязательное вычисление второго операнда, если выражение логического И имеет значение false. Такое сокращенное вычисление можно использовать для предотвращения разыменования пустого указателя, как показано в следующем примере.  
  
```  
char *pch = 0;  
...  
(pch) && (*pch = 'a');  
```  
  
 Если `pch` имеет значение NULL (0), правая часть выражения никогда не вычисляется. Поэтому присваивание с помощью пустого указателя невозможно.  
  
## <a name="operator-keyword-for-"></a>Ключевое слово оператора &&  
 **И** оператор является текстовым эквивалентом **&&**. Существует два способа доступа к **и** оператор в программах: включить файл заголовка `iso646.h`, или выполнить компиляцию с [/Za](../build/reference/za-ze-disable-language-extensions.md) параметр компилятора (отключить расширения языка).  
  
## <a name="example"></a>Пример  
  
```  
// expre_Logical_AND_Operator.cpp  
// compile with: /EHsc  
// Demonstrate logical AND  
#include <iostream>  
  
using namespace std;  
  
int main() {  
   int a = 5, b = 10, c = 15;  
   cout  << boolalpha  
         << "The true expression "  
         << "a < b && b < c yields "  
         << (a < b && b < c) << endl  
         << "The false expression "  
         << "a > b && b < c yields "  
         << (a > b && b < c) << endl;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Операторы C++ встроенные приоритет и ассоциативность операторов](cpp-built-in-operators-precedence-and-associativity.md) [C++ встроенные операторы, приоритет и ассоциативность операторов](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Логические операторы в C](../c-language/c-logical-operators.md)