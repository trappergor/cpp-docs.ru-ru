---
title: Ошибка компилятора C2846
ms.date: 11/04/2016
f1_keywords:
- C2846
helpviewer_keywords:
- C2846
ms.assetid: bc090ec2-5410-4112-9ec6-261325374375
ms.openlocfilehash: 4e1e88e538008cff03349a35e193b7bcd471b950
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50427889"
---
# <a name="compiler-error-c2846"></a>Ошибка компилятора C2846

«конструктор»: интерфейс не может иметь конструктор

Visual C++ [интерфейс](../../cpp/interface.md) не может иметь конструктор.

Следующий пример приводит к возникновению ошибки C2846:

```
// C2846.cpp
// compile with: /c
__interface C {
   C();   // C2846 constructor not allowed in an interface
};
```