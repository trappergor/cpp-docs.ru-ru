---
title: 'Оператор побитового исключающего или: ^ | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- operators [C++], bitwise
- exclusive OR operator
- XOR operator
- bitwise operators [C++], OR operator
- ^ operator
- OR operator [C++], bitwise exclusive
- operators [C++], logical
ms.assetid: f9185d85-65d5-4f64-a6d6-679758d52217
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: fe2f64c20c0d741608dfb2631c2e36026a31e8bb
ms.sourcegitcommit: 2b9e8af9b7138f502ffcba64e2721f7ef52af23b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/01/2018
ms.locfileid: "39406680"
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