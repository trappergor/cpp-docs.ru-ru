---
title: Ошибка компилятора C2688
ms.date: 11/04/2016
f1_keywords:
- C2688
helpviewer_keywords:
- C2688
ms.assetid: 168c9e9d-8f65-4664-af86-db71d3e6ee46
ms.openlocfilehash: cc871467e1e3fb23edc6231c3adb182f5e26c0d8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760248"
---
# <a name="compiler-error-c2688"></a>Ошибка компилятора C2688

"C2:: ФГрВ": ковариантные возвраты с несколькими или виртуальными наследованиями не поддерживаются для функций varargs

Ковариантные возвращаемые типы не поддерживаются C++ в визуальном элементе, если функция содержит переменные аргументы.

Чтобы устранить эту ошибку, определите функции, чтобы они не использовали переменные аргументы, или сделайте возвращаемые значения одинаковыми для всех виртуальных функций.

Следующий пример приводит к возникновению ошибки C2688:

```cpp
// C2688.cpp
struct G1 {};
struct G2 {};
struct G3 : G1, G2 {};
struct G4 {};
struct G5 {};
struct G6 : G4, G5 {};
struct G7 : G3, G6 {};

struct C1 {
   virtual G4& fgrv(int,...);
};

struct C2 : C1 {
   virtual G7& fgrv(int,...);   // C2688, does not return G4&
};
```
