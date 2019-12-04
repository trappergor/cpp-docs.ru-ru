---
title: Ошибка компилятора C2790
ms.date: 11/04/2016
f1_keywords:
- C2790
helpviewer_keywords:
- C2790
ms.assetid: 38d4fce1-ba00-413d-8bc1-e8aa43d7bc1f
ms.openlocfilehash: c63fe7bb3686692818337e890de7fe4c80a18158
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74739562"
---
# <a name="compiler-error-c2790"></a>Ошибка компилятора C2790

"Super": это ключевое слово можно использовать только в теле функции члена класса

Это сообщение об ошибке появляется, если пользователь когда-либо пытается использовать ключевое слово [Super](../../cpp/super.md) вне контекста функции-члена.

Следующий пример приводит к возникновению ошибки C2790:

```cpp
// C2790.cpp
void f() {
   __super::g();   // C2790
}
```
