---
title: Ошибка компилятора C2572
ms.date: 11/04/2016
f1_keywords:
- C2572
helpviewer_keywords:
- C2572
ms.assetid: f1a42d69-727d-4ce5-88c8-d5f55dea66ac
ms.openlocfilehash: ed2e9771d1a407b947926a6f0d8beeb51e724ac7
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755490"
---
# <a name="compiler-error-c2572"></a>Ошибка компилятора C2572

"класс:: член": переопределение параметра по умолчанию: param параметра

Параметры по умолчанию нельзя переопределить. Если для параметра требуется другое значение, параметр по умолчанию должен остаться неопределенным.

Следующий пример приводит к возникновению ошибки C2572:

```cpp
// C2572.cpp
// compile with: /c
void f(int i = 1);   // function declaration

// function definition
void f(int i = 1) {}   // C2572

// try the following line instead
// void f(int i) {}
```
