---
title: Ошибка компилятора C3199
ms.date: 11/04/2016
f1_keywords:
- C3199
helpviewer_keywords:
- C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
ms.openlocfilehash: 2f0ca98dc44a78adde378a0f80078ae30c590e11
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738821"
---
# <a name="compiler-error-c3199"></a>Ошибка компилятора C3199

Недопустимое использование директив pragma с плавающей запятой: исключения не поддерживаются в режиме без точности

Директива pragma [float_control](../../preprocessor/float-control.md) использовалась для указания модели исключения с плавающей запятой в параметре [/FP](../../build/reference/fp-specify-floating-point-behavior.md) , отличном от **/FP: точнее**.

Следующий пример приводит к возникновению ошибки C3199:

```cpp
// C3199.cpp
// compile with: /fp:fast
#pragma float_control(except, on)   // C3199
```
