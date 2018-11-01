---
title: Ошибка компилятора C2256
ms.date: 11/04/2016
f1_keywords:
- C2256
helpviewer_keywords:
- C2256
ms.assetid: 171fa2bc-8c72-49cd-afe5-d723b7acd3c5
ms.openlocfilehash: 56c4df338feb2c0f406835c1ef2ffeeb7caf8bca
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50582718"
---
# <a name="compiler-error-c2256"></a>Ошибка компилятора C2256

Недопустимое использование спецификатора friend для «function»

Деструктор или конструктор не может быть указан как [friend](../../cpp/friend-cpp.md).

Следующий пример приводит к возникновению ошибки C2256:

```
// C2256.cpp
// compile with: /c
class C {
public:
   friend ~C();   // C2256
   ~C();   // OK
};
```