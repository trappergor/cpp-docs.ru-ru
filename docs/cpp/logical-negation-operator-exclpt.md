---
title: 'Оператор логического отрицания: !'
ms.date: 08/27/2018
f1_keywords:
- '!'
- Not
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
ms.openlocfilehash: 7b37e5108ca01d782c13508c0cd7a96b096cd745
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50493736"
---
# <a name="logical-negation-operator-"></a>Оператор логического отрицания: !

## <a name="syntax"></a>Синтаксис

```
! cast-expression
```

## <a name="remarks"></a>Примечания

Оператор логического отрицания (**!**) меняет значение своего операнда. Операнд должен иметь арифметический тип или тип указателя (либо выражение, результатом которого является арифметический тип или тип указателя). Операнд неявно преобразуется в тип **bool**. Результат имеет значение TRUE, если преобразованный операнд — FALSE. Результатом является значение FALSE, если преобразованный операнд имеет значение TRUE. Результат имеет тип **bool**.

Для выражения *e*, унарное выражение `!e` эквивалентно выражению `(e == 0)`, за исключением случаев, когда используются перегруженные операторы.

## <a name="operator-keyword-for-"></a>Ключевое слово оператора для !

**Не** оператор является вариант написания из **!**. Существует два способа для доступа к **не** оператор в программах: включить файл заголовка \<iso646.h >, или выполнить компиляцию с [/Za](../build/reference/za-ze-disable-language-extensions.md) параметр компилятора (отключить расширения языка).

## <a name="example"></a>Пример

```cpp
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

## <a name="see-also"></a>См. также

[Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)<br/>
[Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Унарные арифметические операторы](../c-language/unary-arithmetic-operators.md)<br/>
