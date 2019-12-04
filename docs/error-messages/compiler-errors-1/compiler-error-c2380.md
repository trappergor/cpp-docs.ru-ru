---
title: Ошибка компилятора C2380
ms.date: 11/04/2016
f1_keywords:
- C2380
helpviewer_keywords:
- C2380
ms.assetid: 717b1e6e-ddfe-4bac-a5f3-7f9a4dcb1572
ms.openlocfilehash: ca249bc592bd66c2e461a37fdc18204077f51db2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745438"
---
# <a name="compiler-error-c2380"></a>Ошибка компилятора C2380

типы перед "идентификатором" (конструктор с возвращаемым типом или недопустимое переопределение текущего имени класса?)

Конструктор возвращает значение или переопределяет имя класса.

При компиляции следующего примера возникнет ошибка C2326:

```cpp
// C2380.cpp
// compile with: /c
class C {
public:
   int C();   // C2380, specifies an int return
   int C;   // C2380, redefinition of i
   C();   // OK
};
```
