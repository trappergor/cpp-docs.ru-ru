---
title: Ошибка компилятора C3120
ms.date: 11/04/2016
f1_keywords:
- C3120
helpviewer_keywords:
- C3120
ms.assetid: 9b6b210f-9948-4517-a4cc-b4aaadebde68
ms.openlocfilehash: 99d6280420111fde1a2e2187e3cbaeb529652d01
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50602674"
---
# <a name="compiler-error-c3120"></a>Ошибка компилятора C3120

«имя_метода»: методы интерфейса не может принимать переменное число аргументов

Метод интерфейса не могут принимать переменное число аргументов. Например следующее определение интерфейса создает ошибку C3120:

```
// C3120.cpp
__interface A {
int X(int i, ...);    // C3120
};

int main(void) { return(0); }
```