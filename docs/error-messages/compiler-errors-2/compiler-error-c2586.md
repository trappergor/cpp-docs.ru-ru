---
title: Ошибка компилятора C2586
ms.date: 11/04/2016
f1_keywords:
- C2586
helpviewer_keywords:
- C2586
ms.assetid: dae703c7-5c38-4db6-8411-4d1b22713eb5
ms.openlocfilehash: a6af49bba84eded7d530f6ecc37fac8f6acf16e2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50519851"
---
# <a name="compiler-error-c2586"></a>Ошибка компилятора C2586

синтаксис неверное преобразование определяемых пользователем: недопустимые косвенные обращения

Косвенное обращение оператора преобразования не допускается.

Следующий пример приводит к возникновению ошибки C2586:

```
// c2586.cpp
// compile with: /c
struct C {
   * operator int();   // C2586
   operator char();   // OK
};
```