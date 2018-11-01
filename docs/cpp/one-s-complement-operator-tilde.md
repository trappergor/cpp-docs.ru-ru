---
title: 'Один&#39;s оператор дополнения до единицы: ~'
ms.date: 11/04/2016
f1_keywords:
- "~"
helpviewer_keywords:
- tilde (~) one's complement operator
- one's complement operator
- bitwise-complement operator
- compl operator
- ~ operator [C++], syntax
ms.assetid: 4bf81967-34f7-4b4b-aade-fd03d5da0174
ms.openlocfilehash: d8fb8ca56932669ff85646f2aa0c10691122013b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50469785"
---
# <a name="one39s-complement-operator-"></a>Один&#39;s оператор дополнения до единицы: ~

## <a name="syntax"></a>Синтаксис

```
~ cast-expression
```

## <a name="remarks"></a>Примечания

Оператор дополнения до единицы (`~`), иногда называемый оператором поразрядного отрицания, дополняет свой операнд до единицы в каждом разряде. То есть каждый бит, равный в операнде 1, в результате становится равным 0, а каждый бит, равный в операнде 0, в результате становится равным 1. Операнд оператора дополнения до единицы должен быть целочисленного типа.

## <a name="operator-keyword-for-"></a>Ключевое слово оператора ~

**Compl** оператор является текстовым эквивалентом `~`. Существует два способа для доступа к **compl** оператор в программах: включить файл заголовка `iso646.h`, или выполнить компиляцию с [/Za](../build/reference/za-ze-disable-language-extensions.md).

## <a name="example"></a>Пример

```cpp
// expre_One_Complement_Operator.cpp
// compile with: /EHsc
#include <iostream>

using namespace std;

int main () {
   unsigned short y = 0xFFFF;
   cout << hex << y << endl;
   y = ~y;   // Take one's complement
   cout << hex << y << endl;
}
```

В этом примере новое значение, присвоенное переменной `y`, является дополнением до единицы значения 0xFFFF без знака, т. е. значением 0x0000.

Над целочисленными операндами выполняется восходящее приведение целого типа, и результирующим типом является тип, до которого повышается уровень операнда. См. в разделе [стандартные преобразования](standard-conversions.md) Дополнительные сведения о том, как выполняется такое повышение.

## <a name="see-also"></a>См. также

[Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)<br/>
[Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Унарные арифметические операторы](../c-language/unary-arithmetic-operators.md)