---
title: Ошибка компилятора C2153
ms.date: 11/04/2016
f1_keywords:
- C2153
helpviewer_keywords:
- C2153
ms.assetid: cfc50cb7-9a0f-4b5b-879a-d419c99f7be1
ms.openlocfilehash: eeb7da509ffb1b8c408763c79d471586eb94f383
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605937"
---
# <a name="compiler-error-c2153"></a>Ошибка компилятора C2153

шестнадцатеричные константы должны содержать по крайней мере одну шестнадцатеричную цифру

Шестнадцатеричные константы 0 x "," 0 X и \x не допускаются. Должны соответствовать по крайней мере одну шестнадцатеричную цифру x или X.

Следующий пример приводит к возникновению ошибки C2153:

```
// C2153.cpp
int main() {
   int a= 0x;    // C2153
   int b= 0xA;   // OK
}
```