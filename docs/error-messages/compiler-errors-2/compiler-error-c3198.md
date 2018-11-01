---
title: Ошибка компилятора C3198
ms.date: 11/04/2016
f1_keywords:
- C3198
helpviewer_keywords:
- C3198
ms.assetid: ec4ecf61-0067-4aa4-b443-a91013a1e59d
ms.openlocfilehash: 61a3d14f9ad47edaa1e9b9f2b25d38b8dae7165c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50567457"
---
# <a name="compiler-error-c3198"></a>Ошибка компилятора C3198

Недопустимое использование директив pragma с плавающей точкой: директива fenv_access действует только в точном режиме

[fenv_access](../../preprocessor/fenv-access.md) pragma используется в разделе [/FP](../../build/reference/fp-specify-floating-point-behavior.md) параметров, отличных от **/fp: точное**.

Следующий пример приводит к возникновению ошибки C3198:

```
// C3198.cpp
// compile with: /fp:fast
#pragma fenv_access(on)   // C3198
```