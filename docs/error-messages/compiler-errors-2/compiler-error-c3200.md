---
title: Ошибка компилятора C3200
ms.date: 11/04/2016
f1_keywords:
- C3200
helpviewer_keywords:
- C3200
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
ms.openlocfilehash: 7f6b514231bcda18404e891e0acbe457c8f95146
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74738782"
---
# <a name="compiler-error-c3200"></a>Ошибка компилятора C3200

"шаблон": недопустимый аргумент шаблона для параметра шаблона "параметр", требуется шаблон класса

Передан недопустимый аргумент в шаблон класса. Шаблон класса принимает шаблон в качестве параметра. В следующем примере вызов `Y<int, int> aY` создаст C3200. Первый параметр должен быть шаблоном, например `Y<X, int> aY`.

```cpp
// C3200.cpp
template<typename T>
class X
{
};

template<template<typename U> class T1, typename T2>
class Y
{
};

int main()
{
   Y<int, int> y;   // C3200
}
```
