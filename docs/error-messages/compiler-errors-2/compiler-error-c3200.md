---
title: Ошибка компилятора C3200
ms.date: 11/04/2016
f1_keywords:
- C3200
helpviewer_keywords:
- C3200
ms.assetid: 44bb5e77-f0ec-421c-a732-b9ee7c0a3529
ms.openlocfilehash: 7eb0c00f4f4c5c59766bf305acfef89e12a6cfb1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50505070"
---
# <a name="compiler-error-c3200"></a>Ошибка компилятора C3200

«шаблон»: недопустимый аргумент шаблона для параметра шаблона «параметр», требуется класс-шаблон

Передан недопустимый аргумент для шаблона класса. Шаблон класса ожидает в качестве параметра шаблона. В следующем примере вызов `Y<int, int> aY` создаст C3200. Первый параметр должен быть шаблоном, такой как `Y<X, int> aY`.

```
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