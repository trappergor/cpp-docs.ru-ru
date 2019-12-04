---
title: Ошибка компилятора C2389
ms.date: 11/04/2016
f1_keywords:
- C2389
helpviewer_keywords:
- C2389
ms.assetid: 6122dc81-4ee3-49a5-a67d-d867808c9bac
ms.openlocfilehash: 587a1fcdb5f8d4fbb922b8896cab27a351e0584a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745087"
---
# <a name="compiler-error-c2389"></a>Ошибка компилятора C2389

"оператор": недопустимый операнд nullptr

`nullptr` не может являться операндом.

В следующем примере возникает ошибка C2389:

```cpp
// C2389.cpp
// compile with: /clr
int main() {
   throw nullptr;   // C2389
}
```
