---
title: Ошибка компилятора C2488
ms.date: 11/04/2016
f1_keywords:
- C2488
helpviewer_keywords:
- C2488
ms.assetid: cd435909-43e4-43c6-a57c-5d02468ef75f
ms.openlocfilehash: 9b49d49c8a261bb3d636446f820a45699361830f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452121"
---
# <a name="compiler-error-c2488"></a>Ошибка компилятора C2488

«Идентификатор»: «naked» может применяться только для определения функций, не являющихся членами

[С атрибутом naked](../../cpp/naked-cpp.md) атрибут был применен к объявлению функции.

Следующий пример приводит к возникновению ошибки C2488:

```
// C2488.cpp
// compile with: /c
// processor: x86
__declspec( naked ) void func();   // C2488  declaration, not definition
__declspec( naked ) void i;   // C2488  i is not a function

__declspec( naked ) void func() {}   // OK
```