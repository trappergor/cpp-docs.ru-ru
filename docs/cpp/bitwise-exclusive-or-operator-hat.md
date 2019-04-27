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
ms.openlocfilehash: 07af1b507cf256b84ac2f0f2db4061790a23555a
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62232018"
---
# <a name="bitwise-exclusive-or-operator-"></a>Битовый оператор ИЛИ (исключительное): ^

## <a name="syntax"></a>Синтаксис

```
expression ^ expression
```

## <a name="remarks"></a>Примечания

Оператор побитового исключающего или (**^**) сравнивает каждый бит первого операнда с соответствующим битом второго операнда. Если один бит равен 0, а другой равен 1, соответствующий бит результата устанавливается равным 1. в противном случае — нулю.

Оба операнда оператора побитового эксклюзивного ИЛИ должны быть целочисленного типа. Обычные арифметические преобразования, описанные в [стандартные преобразования](standard-conversions.md) применяются к операндам.

## <a name="operator-keyword-for-"></a>Ключевое слово оператора ^

**Xor** оператор является текстовым эквивалентом **^**. Существует два способа для доступа к **xor** оператор в программах: включить файл заголовка `iso646.h`, или выполнить компиляцию с [/Za](../build/reference/za-ze-disable-language-extensions.md) параметр компилятора (отключить расширения языка).

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

## <a name="see-also"></a>См. также

[Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)