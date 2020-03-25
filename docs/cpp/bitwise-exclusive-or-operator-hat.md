---
title: 'Битовый оператор ИЛИ (исключительное): ^'
ms.date: 11/04/2016
helpviewer_keywords:
- operators [C++], bitwise
- exclusive OR operator
- XOR operator
- bitwise operators [C++], OR operator
- ^ operator
- OR operator [C++], bitwise exclusive
- operators [C++], logical
ms.assetid: f9185d85-65d5-4f64-a6d6-679758d52217
ms.openlocfilehash: 9a44dc60a985729aae79ed0e2e48c44adace647b
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80190720"
---
# <a name="bitwise-exclusive-or-operator-"></a>Битовый оператор ИЛИ (исключительное): ^

## <a name="syntax"></a>Синтаксис

```
expression ^ expression
```

## <a name="remarks"></a>Remarks

Оператор побитового исключающего или ( **^** ) сравнивает каждый бит своего первого операнда с соответствующим битом второго операнда. Если один из битов равен 0, а второй равен 1, соответствующий бит результата устанавливается в 1. В противном случае соответствующий бит результата равен 0.

Оба операнда оператора побитового эксклюзивного ИЛИ должны быть целочисленного типа. Обычные арифметические преобразования, охваченные [стандартными](standard-conversions.md) преобразованиями, применяются к операндам.

## <a name="operator-keyword-for-"></a>Ключевое слово оператора ^

Оператор **XOR** — это текст, эквивалентный **^** . Существует два способа доступа к оператору **XOR** в программах: включите файл заголовка `iso646.h`или Скомпилируйте с параметром компилятора [/Za](../build/reference/za-ze-disable-language-extensions.md) (отключить расширения языка).

## <a name="example"></a>Пример

```cpp
// expre_Bitwise_Exclusive_OR_Operator.cpp
// compile with: /EHsc
// Demonstrate bitwise exclusive OR
#include <iostream>
using namespace std;
int main() {
   unsigned short a = 0x5555;      // pattern 0101 ...
   unsigned short b = 0xFFFF;      // pattern 1111 ...

   cout  << hex << ( a ^ b ) << endl;   // prints "aaaa" pattern 1010 ...
}
```

## <a name="see-also"></a>См. также раздел

[Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
