---
title: Ошибка компилятора C2272
ms.date: 11/04/2016
f1_keywords:
- C2272
helpviewer_keywords:
- C2272
ms.assetid: 1517706a-9c27-452e-9b10-3424b3d232bc
ms.openlocfilehash: 1a5a1e47a721cb6edd795012cc45943e63708936
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50537428"
---
# <a name="compiler-error-c2272"></a>Ошибка компилятора C2272

«функция»: модификаторы недопустимы для статических функций-членов

Объект `static` функция-член объявлен с описателем модели памяти, таких как [const](../../cpp/const-cpp.md) или [volatile](../../cpp/volatile-cpp.md), и такие модификаторы недопустимы для `static` функций-членов.

Следующий пример приводит к возникновению ошибки C2272:

```
// C2272.cpp
// compile with: /c
class CMyClass {
public:
   static void func1() const volatile;   // C2272  func1 is static
   void func2() const volatile;   // OK
};
```