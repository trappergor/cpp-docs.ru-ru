---
title: Ошибка компилятора C2733
ms.date: 11/04/2016
f1_keywords:
- C2733
helpviewer_keywords:
- C2733
ms.assetid: 67f83561-c633-407c-a2ee-f9fd16e165bf
ms.openlocfilehash: 3ef669a49f4a3ec5a1af1a15a79f2511fa2699dd
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755789"
---
# <a name="compiler-error-c2733"></a>Ошибка компилятора C2733

Вторая C компоновка перегруженной функции "функция" запрещена

С компоновкой C объявлено более одной перегруженной функции. При использовании компоновки C только одна форма указанной функции может быть внешней. Так как перегруженные функции имеют одно и то же недекорированное имя, их нельзя использовать с программами на языке C.

Следующий пример приводит к возникновению ошибки C2733:

```cpp
// C2733.cpp
extern "C" {
   void F1(int);
}

extern "C" {
   void F1();   // C2733
   // try the following line instead
   // void F2();
}
```
