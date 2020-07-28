---
title: Ошибка компилятора C2272
ms.date: 11/04/2016
f1_keywords:
- C2272
helpviewer_keywords:
- C2272
ms.assetid: 1517706a-9c27-452e-9b10-3424b3d232bc
ms.openlocfilehash: e4163d68e0fbfea062279ba91e2c902855245e4a
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87220396"
---
# <a name="compiler-error-c2272"></a>Ошибка компилятора C2272

"функция": модификаторы недопустимы для статических функций члена

**`static`** Функция-член объявлена с описателем модели памяти, например [const](../../cpp/const-cpp.md) или [volatile](../../cpp/volatile-cpp.md), и такие модификаторы не допускаются в **`static`** функциях-членах.

Следующий пример приводит к возникновению ошибки C2272:

```cpp
// C2272.cpp
// compile with: /c
class CMyClass {
public:
   static void func1() const volatile;   // C2272  func1 is static
   void func2() const volatile;   // OK
};
```
