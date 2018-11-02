---
title: Ошибка компилятора C2055
ms.date: 11/04/2016
f1_keywords:
- C2055
helpviewer_keywords:
- C2055
ms.assetid: 6cec79cc-6bec-443f-9897-fbf5452718c7
ms.openlocfilehash: 3c198168b4445e619148e5611621fa3ddba95d6b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597279"
---
# <a name="compiler-error-c2055"></a>Ошибка компилятора C2055

требуется список формальных параметров, а не список типов

Определение функции содержит список параметров типа вместо списка формальных параметров. ANSI C требует формальных параметров, чтобы присвоить имя, если они не являются пустыми или многоточием (`...`).

Следующий пример приводит к возникновению ошибки C2055:

```
// C2055.c
// compile with: /c
void func(int, char) {}  // C2055
void func (int i, char c) {}   // OK
```