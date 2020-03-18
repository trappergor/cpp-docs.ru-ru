---
title: 'Оператор логического отрицания: !'
ms.date: 08/27/2018
f1_keywords:
- '!'
helpviewer_keywords:
- '! operator'
- NOT operator
- logical negation
ms.assetid: 650add9f-a7bc-426c-b01d-5fc6a81c8b62
ms.openlocfilehash: 06142ef15fcdbafdbae4b892772a04b117c087f6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79446537"
---
# <a name="logical-negation-operator-"></a>Оператор логического отрицания: !

## <a name="syntax"></a>Синтаксис

```
! cast-expression
```

## <a name="remarks"></a>Remarks

Оператор логического отрицания ( **!** ) меняет значение операнда на противоположное. Операнд должен иметь арифметический тип или тип указателя (либо выражение, результатом которого является арифметический тип или тип указателя). Операнд неявно преобразуется в тип **bool**. Результат имеет значение TRUE, если преобразованный операнд имеет значение FALSE; результат равен FALSE, если преобразованный операнд имеет значение TRUE. Результат имеет тип **bool**.

Для выражения *e*`!e` унарное выражение эквивалентно выражению `(e == 0)`, за исключением случаев, когда задействованы перегруженные операторы.

## <a name="operator-keyword-for-"></a>Ключевое слово оператора для !

Оператор **Not** является альтернативным написанием **!** . Существует два способа доступа к оператору **Not** в программах: Включите заголовочный файл \<iso646. h > или Скомпилируйте с параметром компилятора [/Za](../build/reference/za-ze-disable-language-extensions.md) (отключить расширения языка).

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

## <a name="see-also"></a>См. также раздел

[Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)<br/>
[Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Унарные арифметические операторы](../c-language/unary-arithmetic-operators.md)<br/>
