---
title: Ошибка компилятора C2503
ms.date: 11/04/2016
f1_keywords:
- C2503
helpviewer_keywords:
- C2503
ms.assetid: da86cc89-fd04-400b-aa8d-a5ffaf7e3918
ms.openlocfilehash: c481a27f19a92f47a19f0cfaa7b59cd509bb3c15
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50660815"
---
# <a name="compiler-error-c2503"></a>Ошибка компилятора C2503

«класс»: базовые классы не могут содержать массивы нулевого размера

Базовый класс или структура содержит массив нулевого размера. Массив, в классе должен иметь по крайней мере один элемент.

Следующий пример приводит к возникновению ошибки C2503:

```
// C2503.cpp
// compile with: /c
class A {
   public:
   int array [];
};

class B : A {};    // C2503

class C {
public:
   int array [10];
};

class D : C {};
```