---
title: 'Операторы равенства: == и !='
ms.date: 11/04/2016
f1_keywords:
- '!='
- ==
helpviewer_keywords:
- '!= operator'
- equality operator
- not equal to comparison operator
- equality operator [C++], syntax
- == operator
- not_eq operator
- equal to operator
ms.assetid: ba4e9659-2392-4fb4-be5a-910a2a6df45a
ms.openlocfilehash: 8a0c08f438528caeaac6d5e52e806a36fe56dd25
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80189251"
---
# <a name="equality-operators--and-"></a>Операторы равенства: == и !=

## <a name="syntax"></a>Синтаксис

```
expression == expression
expression != expression
```

## <a name="remarks"></a>Remarks

Бинарные операторы равенства сравнивают операнды для строгого равенства или неравенства.

Операторы равенства, то есть равно (`==`) и не равно (`!=`), имеют более низкий приоритет, чем операторы отношения, но их поведение аналогично. Тип результата для этих операторов — **bool**.

Оператор Equal-to (`==`) возвращает **значение true** (1), если оба операнда имеют одинаковое значение; в противном случае возвращается **значение false** (0). Оператор "не равно" (`!=`) возвращает **значение true** , если операнды имеют разные значения; в противном случае возвращается **значение false**.

## <a name="operator-keyword-for-"></a>Ключевое слово оператора !=

Текстовым эквивалентом оператора `not_eq` является оператор `!=`. Есть два способа получить доступ к оператору `not_eq` в программах: включить файл заголовка `iso646.h`или выполнить компиляцию с параметром компилятора [/Za](../build/reference/za-ze-disable-language-extensions.md) (отключить расширения языка).

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

Операторы равенства могут сравнивать указатели на члены одного типа. В таких сравнениях выполняются преобразования указателей на члены. Указатели на члены также можно сравнить с константным выражением, результатом которого является значение 0.

## <a name="see-also"></a>См. также раздел

[Выражения с бинарными операторами](../cpp/expressions-with-binary-operators.md)<br/>
[Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Операторы отношения и равенства C](../c-language/c-relational-and-equality-operators.md)
