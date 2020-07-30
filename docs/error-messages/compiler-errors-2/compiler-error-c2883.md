---
title: Ошибка компилятора C2883
ms.date: 11/04/2016
f1_keywords:
- C2883
helpviewer_keywords:
- C2883
ms.assetid: 5c6d689d-ed42-41ad-b5c0-e9c2e0b8c356
ms.openlocfilehash: fcd97a2f362e50ec856e53da2603c29e07595670
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87233474"
---
# <a name="compiler-error-c2883"></a>Ошибка компилятора C2883

"имя": объявление функции конфликтует с "идентификатором", представленным с помощью объявления using

Вы попытались определить функцию несколько раз. Первое определение было создано из пространства имен с **`using`** объявлением. Второй является локальным определением.

Следующий пример приводит к возникновению ошибки C2883:

```cpp
// C2883.cpp
namespace A {
   void z(int);
}

int main() {
   using A::z;
   void z(int);   // C2883  z is already defined
}
```
