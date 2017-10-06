---
title: "Операторы равенства: == и! = | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- not_eq
- '!='
- ==
dev_langs:
- C++
helpviewer_keywords:
- '!= operator'
- equality operator
- not equal to comparison operator
- equality operator [C++], syntax
- == operator
- not_eq operator
- equal to operator
ms.assetid: ba4e9659-2392-4fb4-be5a-910a2a6df45a
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 5412869204f088e321d2a41da407026f9447eb82
ms.contentlocale: ru-ru
ms.lasthandoff: 09/25/2017

---
# <a name="equality-operators--and-"></a>Операторы равенства: == и !=
## <a name="syntax"></a>Синтаксис  
  
```  
expression == expression  
expression != expression  
```  
  
## <a name="remarks"></a>Примечания  
 Бинарные операторы равенства сравнивают операнды для строгого равенства или неравенства.  
  
 Операторы равенства, то есть равно (`==`) и не равно (`!=`), имеют более низкий приоритет, чем операторы отношения, но их поведение аналогично. Результат этих операторов будет принадлежать типу `bool`.  
  
 Оператор равенства для (`==`) возвращает **true** (1), если оба операнда имеют одинаковые значения; в противном случае возвращается **false** (0). Оператор не равно (`!=`) возвращает **true** Если операнды имеют неравные значения; в противном случае он возвращает **false**.  
  
## <a name="operator-keyword-for-"></a>Ключевое слово оператора !=  
 Текстовым эквивалентом оператора `not_eq` является оператор `!=`. Существует два способа доступа к `not_eq` оператор в программах: включить файл заголовка `iso646.h`, или выполнить компиляцию с [/Za](../build/reference/za-ze-disable-language-extensions.md) параметр компилятора (отключить расширения языка).  
  
## <a name="example"></a>Пример  
  
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
  
 Операторы равенства могут сравнивать указатели на члены одного типа. При таком сравнении выполняются преобразования указателей на члены. Указатели на члены также можно сравнить с константным выражением, результатом которого является значение 0.  
  
## <a name="see-also"></a>См. также  
 [Выражения с бинарными операторами](../cpp/expressions-with-binary-operators.md)   
 [Встроенный C++ операторы, приоритет и ассоциативность операторов](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Операторы отношения и равенства C](../c-language/c-relational-and-equality-operators.md)
