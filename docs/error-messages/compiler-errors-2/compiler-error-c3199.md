---
title: Ошибка компилятора C3199
ms.date: 11/04/2016
f1_keywords:
- C3199
helpviewer_keywords:
- C3199
ms.assetid: e7a478d3-115a-40a3-991b-c7454fd2e28e
ms.openlocfilehash: 934e980149ad893e6799b0ab119a148fc5652fdc
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62402792"
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