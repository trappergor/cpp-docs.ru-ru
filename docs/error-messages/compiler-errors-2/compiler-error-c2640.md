---
title: Ошибка компилятора C2640
ms.date: 11/04/2016
f1_keywords:
- C2640
helpviewer_keywords:
- C2640
ms.assetid: e4d137ab-ed1d-457c-9eec-b70d97f1b0b4
ms.openlocfilehash: 75acfa4d702b31052b7113117c71bf66ed9de149
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758246"
---
# <a name="compiler-error-c2640"></a>Ошибка компилятора C2640

"идентификатор": недопустимый модификатор __based для ссылки

Модификатор `__based` можно использовать только для указателей.

Следующий пример приводит к возникновению ошибки C2640:

```cpp
// C2640.cpp
void f(int i) {
    void *vp;
    int _based(vp) &vr = I;  // C2640
}
```
