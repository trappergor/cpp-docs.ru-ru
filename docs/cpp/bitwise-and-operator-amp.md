---
title: 'Оператор побитового и: &amp;'
ms.date: 11/04/2016
helpviewer_keywords:
- AND operator
- bitwise operators [C++], AND operator
- '& operator [C++], bitwise operators'
ms.assetid: 76f40de3-c417-47b9-8a77-532f3fc990a5
ms.openlocfilehash: b5c99d19be3461b10a1126dea3a45d308c0fc558
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80181295"
---
# <a name="bitwise-and-operator-amp"></a>Оператор побитового и: &amp;

## <a name="syntax"></a>Синтаксис

```
expression & expression
```

## <a name="remarks"></a>Remarks

Выражения могут представлять собой другие and-выражения или (в зависимости от упомянутых ниже типов ограничений) выражения равенства, выражения связей, выражения сложения, выражения умножения, выражения указателя на член, выражения приведения, унарные выражения, постфиксные выражения или основные выражения.

Оператор побитового и ( **&** ) сравнивает каждый бит первого операнда с соответствующим битом второго операнда. Если оба бита равны 1, соответствующий бит результата равен 1. В противном случае соответствующий бит результата равен 0.

Оба операнда оператора побитового И должны иметь целочисленный тип. Обычные арифметические преобразования, охваченные [стандартными преобразованиями](standard-conversions.md), применяются к операндам.

## <a name="operator-keyword-for-"></a>Ключевое слово оператора для &

Оператор **BITAND** является текстовым эквивалентом **&** . Существует два способа доступа к оператору **BITAND** в программах: включите файл заголовка `iso646.h`или Скомпилируйте с параметром компилятора [/Za](../build/reference/za-ze-disable-language-extensions.md) (отключить расширения языка).

## <a name="example"></a>Пример

```cpp
// expre_Bitwise_AND_Operator.cpp
// compile with: /EHsc
// Demonstrate bitwise AND
#include <iostream>
using namespace std;
int main() {
   unsigned short a = 0xFFFF;      // pattern 1111 ...
   unsigned short b = 0xAAAA;      // pattern 1010 ...

   cout  << hex << ( a & b ) << endl;   // prints "aaaa", pattern 1010 ...
}
```

## <a name="see-also"></a>См. также раздел

[Встроенные операторы C++, приоритет и ассоциативность](cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Встроенные операторы C++, приоритет и ассоциативность](../cpp/cpp-built-in-operators-precedence-and-associativity.md)<br/>
[Побитовые операторы в C](../c-language/c-bitwise-operators.md)
