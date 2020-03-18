---
title: 'Оператор побитового включающего ИЛИ: |'
ms.date: 06/14/2018
f1_keywords:
- '|'
helpviewer_keywords:
- OR operator [C++], bitwise inclusive
- bitwise operators [C++], OR operator
- inclusive OR operator
- '| operator'
ms.assetid: 4c8a6a68-d828-447d-875a-aedb4ce3aa9a
ms.openlocfilehash: 0df3493930206d655c0d9bca8a2468151aa3c2c6
ms.sourcegitcommit: 63784729604aaf526de21f6c6b62813882af930a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/17/2020
ms.locfileid: "79445510"
---
# <a name="bitwise-inclusive-or-operator-"></a>Оператор побитового включающего ИЛИ: |

## <a name="syntax"></a>Синтаксис

> *expression1* **|** *выражение2*

## <a name="remarks"></a>Remarks

Оператор побитового включающего **&#124;** или () сравнивает каждый бит своего первого операнда с соответствующим битом второго операнда. Если какой-либо из битов равен 1, соответствующий бит результата равен 1. В противном случае соответствующий бит результата равен 0.

Оба операнда оператора побитового ИЛИ должны быть целочисленного типа. Обычные арифметические преобразования, охваченные [стандартными](standard-conversions.md) преобразованиями, применяются к операндам.

## <a name="operator-keyword-for-124"></a>Ключевое слово operator для&#124;

Оператор **bitor** является текстовым эквивалентом **&#124;** . Существует два способа доступа к оператору **bitor** в программах: Включите заголовочный файл \<iso646. h > или Скомпилируйте с параметром компилятора [/Za](../build/reference/za-ze-disable-language-extensions.md) (отключить расширения языка).

## <a name="example"></a>Пример

```cpp
// expre_Bitwise_Inclusive_OR_Operator.cpp
// compile with: /EHsc
// Demonstrate bitwise inclusive OR
#include <iostream>
using namespace std;

int main() {
   unsigned short a = 0x5555;      // pattern 0101 ...
   unsigned short b = 0xAAAA;      // pattern 1010 ...

   cout  << hex << ( a | b ) << endl;   // prints "ffff" pattern 1111 ...
}
```

## <a name="see-also"></a>См. также раздел

[Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Побитовые операторы в C](../c-language/c-bitwise-operators.md)