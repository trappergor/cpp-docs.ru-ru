---
title: Ошибка компилятора C2884
ms.date: 11/04/2016
f1_keywords:
- C2884
helpviewer_keywords:
- C2884
ms.assetid: 8b4d43e3-3fb5-4360-86c8-de59d8736d4f
ms.openlocfilehash: d6014aa44dd1c2a5f1b0418a7171b239a754ec33
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220201"
---
# <a name="compiler-error-c2884"></a>Ошибка компилятора C2884

"имя": появилось при конфликте объявления using с локальной функцией "функция"

Вы попытались определить функцию несколько раз. Первое определение — это локальное определение. Второй — из пространства имен с **`using`** объявлением.

Следующий пример приводит к возникновению ошибки C2884:

```cpp
// C2884.cpp
namespace A {
   void z(int);
}

void f() {
   void z(int);
   using A::z;   // C2884 z is already defined
}
```
