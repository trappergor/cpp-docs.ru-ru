---
title: 'Оператор&#39;дополнения к одному s: ~'
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
ms.openlocfilehash: 777f253925caf38647863bdaa93fde8d5a03e3f9
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80177720"
---
# <a name="one39s-complement-operator-"></a>Оператор&#39;дополнения к одному s: ~

## <a name="syntax"></a>Синтаксис

```
~ cast-expression
```

## <a name="remarks"></a>Remarks

Оператор дополнения до единицы (`~`), иногда называемый оператором поразрядного отрицания, дополняет свой операнд до единицы в каждом разряде. То есть каждый бит, равный в операнде 1, в результате становится равным 0, а каждый бит, равный в операнде 0, в результате становится равным 1. Операнд оператора дополнения до единицы должен быть целочисленного типа.

## <a name="operator-keyword-for-"></a>Ключевое слово оператора ~

Оператор **comp** является текстовым эквивалентом `~`. Существует два способа доступа к оператору **comp** в программах: включить файл заголовка `iso646.h`или скомпилировать с параметром [/Za](../build/reference/za-ze-disable-language-extensions.md).

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

Над целочисленными операндами выполняется восходящее приведение целого типа, и результирующим типом является тип, до которого повышается уровень операнда. Дополнительные сведения о том, как выполняется продвижение, см. в разделе [стандартные преобразования](standard-conversions.md) .

## <a name="see-also"></a>См. также раздел

[Выражения с унарными операторами](../cpp/expressions-with-unary-operators.md)<br/>
[Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Унарные арифметические операторы](../c-language/unary-arithmetic-operators.md)
