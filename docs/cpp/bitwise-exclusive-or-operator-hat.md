---
title: 'Оператор побитового исключающего ИЛИ: ^'
description: Исключающий и используемый в стандартном языке C++ синтаксис оператора OR.
ms.date: 07/23/2020
f1_keywords:
- xor_cpp
helpviewer_keywords:
- operators [C++], bitwise
- exclusive OR operator
- XOR operator
- bitwise operators [C++], OR operator
- ^ operator
- OR operator [C++], bitwise exclusive
- operators [C++], logical
ms.assetid: f9185d85-65d5-4f64-a6d6-679758d52217
ms.openlocfilehash: 0f64b9f90b70756d29fcabb361cc07abe58e0a54
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87229107"
---
# <a name="bitwise-exclusive-or-operator-"></a>Оператор побитового исключающего ИЛИ: ^

## <a name="syntax"></a>Синтаксис

> *выражение* **`^`** *выражение*

## <a name="remarks"></a>Remarks

Оператор побитового исключающего или ( **`^`** ) сравнивает каждый бит своего первого операнда с соответствующим битом второго операнда. Если бит первого операнда равен 0, а второй бит равен 1, соответствующий бит результата устанавливается в значение 1. в противном случае — нулю.

Оба операнда оператора должны иметь целочисленные типы. Обычные арифметические преобразования, охваченные [стандартными](standard-conversions.md) преобразованиями, применяются к операндам.

## <a name="operator-keyword-for-"></a>Ключевое слово оператора для ^

C++ указывает на **`xor`** альтернативное написание для **`^`** . В языке C в качестве макроса в заголовке указывается альтернативное написание \<iso646.h> . В C++ альтернативным написанием является ключевое слово; использование \<iso646.h> или эквивалент C++ \<ciso646> не рекомендуется. В Microsoft C++ [`/permissive-`](../build/reference/permissive-standards-conformance.md) [`/Za`](../build/reference/za-ze-disable-language-extensions.md) параметр компилятора или необходим для включения альтернативного написания.


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

[Встроенные операторы, приоритет и ассоциативность C++](../cpp/cpp-built-in-operators-precedence-and-associativity.md)
