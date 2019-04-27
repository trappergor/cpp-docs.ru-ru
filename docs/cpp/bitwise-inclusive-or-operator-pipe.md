---
title: 'Побитового исключающего оператора OR: |'
ms.date: 06/14/2018
f1_keywords:
- bitor
- '|'
helpviewer_keywords:
- OR operator [C++], bitwise inclusive
- bitwise operators [C++], OR operator
- inclusive OR operator
- '| operator'
ms.assetid: 4c8a6a68-d828-447d-875a-aedb4ce3aa9a
ms.openlocfilehash: 848bf3b2ec61084b59ab5b1ee6807f6066a4675e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62184297"
---
# <a name="bitwise-inclusive-or-operator-"></a>Побитового исключающего оператора OR: |

## <a name="syntax"></a>Синтаксис

> *expression1* **|** *expression2*

## <a name="remarks"></a>Примечания

Оператора побитового или (**&#124;**) сравнивает каждый бит первого операнда с соответствующим битом второго операнда. Если любой из битов равен единице, соответствующий бит результата устанавливается равным единице, а в противном случае — нулю.

Оба операнда оператора побитового ИЛИ должны быть целочисленного типа. Обычные арифметические преобразования, описанные в [стандартные преобразования](standard-conversions.md) применяются к операндам.

## <a name="operator-keyword-for-124"></a>Ключевое слово оператора&#124;

**Bitor** оператор является текстовым эквивалентом **&#124;**. Существует два способа для доступа к **bitor** оператор в программах: включить файл заголовка \<iso646.h >, или выполнить компиляцию с [/Za](../build/reference/za-ze-disable-language-extensions.md) параметр компилятора (отключить расширения языка).

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

## <a name="see-also"></a>См. также

[Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Побитовые операторы в C](../c-language/c-bitwise-operators.md)