---
title: Ошибка компилятора C3874
ms.date: 11/04/2016
f1_keywords:
- C3874
helpviewer_keywords:
- C3874
ms.assetid: fd55fc05-69a7-4237-b3b7-dca1d5400b4f
ms.openlocfilehash: e46f5934653a0c7cdba463c71c44b10ea28e3bf5
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736702"
---
# <a name="compiler-error-c3874"></a>Ошибка компилятора C3874

возвращаемый тип "функция" должен быть "int", а не "тип"

Функция не имеет возвращаемого типа, ожидаемого компилятором.

Следующий пример приводит к возникновению ошибки C3874:

```cpp
// C3874b.cpp
double main()
{   // C3874
}
```
