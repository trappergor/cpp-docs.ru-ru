---
title: Ошибка компилятора C2846
ms.date: 11/04/2016
f1_keywords:
- C2846
helpviewer_keywords:
- C2846
ms.assetid: bc090ec2-5410-4112-9ec6-261325374375
ms.openlocfilehash: eef558301ce2d623ef78aab40a7a054cd73037df
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74750615"
---
# <a name="compiler-error-c2846"></a>Ошибка компилятора C2846

"Constructor": интерфейс не может иметь конструктор

Визуальный C++ [интерфейс](../../cpp/interface.md) не может иметь конструктор.

Следующий пример приводит к возникновению ошибки C2846:

```cpp
// C2846.cpp
// compile with: /c
__interface C {
   C();   // C2846 constructor not allowed in an interface
};
```
