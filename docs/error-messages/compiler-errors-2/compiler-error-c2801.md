---
title: Ошибка компилятора C2801
ms.date: 11/04/2016
f1_keywords:
- C2801
helpviewer_keywords:
- C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
ms.openlocfilehash: 0d2ea3677d883fa4843c37a41d733872b23cbba0
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760677"
---
# <a name="compiler-error-c2801"></a>Ошибка компилятора C2801

"operator оператор" должен быть не статическим членом

Следующие операторы можно перегружать только как нестатические члены:

- `=` назначения

- `->` доступа к членам класса

- `[]` индексов

- Вызов функции `()`

Возможные причины C2801:

- Перегруженный оператор не является членом класса, структуры или объединения.

- Перегруженный оператор объявлен как `static`.

- Следующий пример приводит к возникновению ошибки C2801:

```cpp
// C2801.cpp
// compile with: /c
operator[]();   // C2801 not a member
class A {
   static operator->();   // C2801 static
   operator()();   // OK
};
```
