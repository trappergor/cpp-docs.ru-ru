---
title: Ошибка компилятора C2502
ms.date: 11/04/2016
f1_keywords:
- C2502
helpviewer_keywords:
- C2502
ms.assetid: affa0b86-15fc-4e17-b7f2-6aad4a3771c4
ms.openlocfilehash: bb0e9cc16d403439dc74ae7c93cfe51e370b199a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87218212"
---
# <a name="compiler-error-c2502"></a>Ошибка компилятора C2502

"идентификатор": слишком много модификаторов доступа для базового класса

Базовый класс имеет более одного модификатора доступа. Допускается только один модификатор доступа ( **`public`** , **`private`** или **`protected`** ).

Следующий пример приводит к возникновению ошибки C2502:

```cpp
// C2502.cpp
// compile with: /c
class A { };
class B { };
class C : private public A { };   // C2502

// OK
class D : private A {};
class E : public A, private B {};
```
