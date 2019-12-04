---
title: Ошибка компилятора C2153
ms.date: 11/04/2016
f1_keywords:
- C2153
helpviewer_keywords:
- C2153
ms.assetid: cfc50cb7-9a0f-4b5b-879a-d419c99f7be1
ms.openlocfilehash: 1f03b196b7ddaae80dac1941cdde5be16acace5f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74748688"
---
# <a name="compiler-error-c2153"></a>Ошибка компилятора C2153

шестнадцатеричные константы должны содержать по крайней мере одну шестнадцатеричную цифру

Шестнадцатеричные константы 0x, 0X и \x недопустимы. По крайней мере одна шестнадцатеричная цифра должна следовать за x или X.

Следующий пример приводит к возникновению ошибки C2153:

```cpp
// C2153.cpp
int main() {
   int a= 0x;    // C2153
   int b= 0xA;   // OK
}
```
