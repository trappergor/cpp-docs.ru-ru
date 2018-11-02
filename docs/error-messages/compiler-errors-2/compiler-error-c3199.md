---
title: Ошибка компилятора C3199
ms.date: 11/04/2016
f1_keywords:
- C3199
helpviewer_keywords:
- C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
ms.openlocfilehash: 934e980149ad893e6799b0ab119a148fc5652fdc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50578963"
---
# <a name="compiler-error-c3199"></a>Ошибка компилятора C3199

Недопустимое использование директив pragma с плавающей точкой: исключения поддерживаются только в точном режиме

[Float_control](../../preprocessor/float-control.md) pragma используется для указания модели исключения с плавающей запятой [/FP](../../build/reference/fp-specify-floating-point-behavior.md) параметров, отличных от **/fp: точное**.

Следующий пример приводит к возникновению ошибки C3199:

```
// C3199.cpp
// compile with: /fp:fast
#pragma float_control(except, on)   // C3199
```