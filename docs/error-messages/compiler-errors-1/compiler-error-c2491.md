---
title: Ошибка компилятора C2491
ms.date: 11/04/2016
f1_keywords:
- C2491
helpviewer_keywords:
- C2491
ms.assetid: 4e5a8f81-124e-402c-a5ec-d35a89b5469e
ms.openlocfilehash: 7ee7fb6e66ca9d5e09ad0eb445262c5f87d2060e
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757076"
---
# <a name="compiler-error-c2491"></a>Ошибка компилятора C2491

'идентификатор' : определение функции dllimport не разрешено

Данные, статические данные-члены могут быть объявлены, как `dllimport`, но не определены как `dllimport`.

Чтобы устранить эту проблему, удалите описатель `__declspec(dllimport)` из определения функции.

Следующий пример приводит к возникновению ошибки C2491:

```cpp
// C2491.cpp
// compile with: /c
// function definition
void __declspec(dllimport) funcB() {}   // C2491

// function declaration
void __declspec(dllimport) funcB();   // OK
```
