---
title: Ошибка компилятора C2256
ms.date: 11/04/2016
f1_keywords:
- C2256
helpviewer_keywords:
- C2256
ms.assetid: 171fa2bc-8c72-49cd-afe5-d723b7acd3c5
ms.openlocfilehash: b362a236953701278c57d2b738a6303e83b7637c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758818"
---
# <a name="compiler-error-c2256"></a>Ошибка компилятора C2256

Недопустимое использование спецификатора Friend в функции "Function"

Деструктор или конструктор не может быть указан как [дружественный](../../cpp/friend-cpp.md).

Следующий пример приводит к возникновению ошибки C2256:

```cpp
// C2256.cpp
// compile with: /c
class C {
public:
   friend ~C();   // C2256
   ~C();   // OK
};
```
