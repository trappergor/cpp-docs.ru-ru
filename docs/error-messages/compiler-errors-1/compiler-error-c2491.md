---
title: Ошибка компилятора C2491
ms.date: 11/04/2016
f1_keywords:
- C2491
helpviewer_keywords:
- C2491
ms.assetid: 4e5a8f81-124e-402c-a5ec-d35a89b5469e
ms.openlocfilehash: 3b48bebde6d7baedea73ed181cd4ea33adc44a69
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62361338"
---
# <a name="compiler-error-c2491"></a>Ошибка компилятора C2491

'идентификатор' : определение функции dllimport не разрешено

Данные, статические данные-члены могут быть объявлены, как `dllimport`, но не определены как `dllimport`.

Чтобы устранить эту проблему, удалите описатель `__declspec(dllimport)` из определения функции.

Следующий пример приводит к возникновению ошибки C2491:

```
// C2491.cpp
// compile with: /c
// function definition
void __declspec(dllimport) funcB() {}   // C2491

// function declaration
void __declspec(dllimport) funcB();   // OK
```