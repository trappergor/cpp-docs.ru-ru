---
title: Ошибка компилятора C2640
ms.date: 11/04/2016
f1_keywords:
- C2640
helpviewer_keywords:
- C2640
ms.assetid: e4d137ab-ed1d-457c-9eec-b70d97f1b0b4
ms.openlocfilehash: eb712379ff3ce25a435f4810f5552bc97f635cdd
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212687"
---
# <a name="compiler-error-c2640"></a>Ошибка компилятора C2640

"идентификатор": недопустимый модификатор __based для ссылки

**`__based`** Модификатор можно использовать только для указателей.

Следующий пример приводит к возникновению ошибки C2640:

```cpp
// C2640.cpp
void f(int i) {
    void *vp;
    int _based(vp) &vr = I;  // C2640
}
```
