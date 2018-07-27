---
title: 'Операторы равенства: == и! = | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: eaf0c52cc9811e84fab026e333ee3c0808d4effd
ms.sourcegitcommit: 1fd1eb11f65f2999dfd93a2d924390ed0a0901ed
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/10/2018
ms.locfileid: "37944729"
---
# <a name="equality-operators--and-"></a>Операторы равенства: == и !=
## <a name="syntax"></a>Синтаксис  
  
```  
expression == expression  
expression != expression  
```  
  
## <a name="remarks"></a>Примечания  
 Бинарные операторы равенства сравнивают операнды для строгого равенства или неравенства.  
  
 Операторы равенства, то есть равно (`==`) и не равно (`!=`), имеют более низкий приоритет, чем операторы отношения, но их поведение аналогично. Тип результата для этих операторов **bool**.  
  
 Оператор равенства для (`==`) возвращает **true** (1), если оба операнда имеют одинаковые значения; в противном случае он возвращает **false** (0). Оператор not равен (`!=`) возвращает **true** Если операнды имеют неравные значения; в противном случае возвращается **false**.  
  
## <a name="operator-keyword-for-"></a>Ключевое слово оператора !=  
 Текстовым эквивалентом оператора `not_eq` является оператор `!=`. Существует два способа для доступа к `not_eq` оператор в программах: включить файл заголовка `iso646.h`, или выполнить компиляцию с [/Za](../build/reference/za-ze-disable-language-extensions.md) параметр компилятора (отключить расширения языка).  
  
## <a name="example"></a>Пример  
  
```cpp 
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
 [Встроенные операторы C++, приоритет и ассоциативность операторов](../cpp/cpp-built-in-operators-precedence-and-associativity.md)   
 [Операторы отношения и равенства C](../c-language/c-relational-and-equality-operators.md)