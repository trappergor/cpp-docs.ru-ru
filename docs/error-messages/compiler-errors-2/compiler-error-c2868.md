---
title: Ошибка компилятора C2868
ms.date: 11/04/2016
f1_keywords:
- C2868
helpviewer_keywords:
- C2868
ms.assetid: 6ff5837b-e66d-44d1-9d17-80af35e08d08
ms.openlocfilehash: 4cb259ed0f43831226fb7e1a1ccf7b28bcef7819
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50614777"
---
# <a name="compiler-error-c2868"></a>Ошибка компилятора C2868

> "*идентификатор*": недопустимый синтаксис для объявления использования; требуется полное имя

Объект [объявление using](../../cpp/using-declaration.md) требует *полное имя*, оператор области действия (`::`) запятыми последовательность имен пространства имен, класса или перечисления, заканчивается имя идентификатора. Один оператор разрешения области действия может использоваться для вводят имя из глобального пространства имен.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2868, а также показано правильное использование:

```cpp
// C2868.cpp
class X {
public:
   int i;
};

class Y : X {
public:
   using X::i;   // OK
};

int main() {
   using X;   // C2868
}
```