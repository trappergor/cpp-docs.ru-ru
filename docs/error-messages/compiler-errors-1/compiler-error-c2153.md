---
title: Ошибка компилятора C2153 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2153
dev_langs:
- C++
helpviewer_keywords:
- C2153
ms.assetid: cfc50cb7-9a0f-4b5b-879a-d419c99f7be1
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: bbb3283ff4d27b6c939434ac3df8f8c1febf0eb3
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46051429"
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