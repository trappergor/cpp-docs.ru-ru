---
title: Ошибка компилятора C2436
ms.date: 11/04/2016
f1_keywords:
- C2436
helpviewer_keywords:
- C2436
ms.assetid: ca4cc813-bc1d-4c0a-9a2c-3a5fe673d084
ms.openlocfilehash: 335d4a304e16814243894c9524a9e4a2a7356110
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50627361"
---
# <a name="compiler-error-c2436"></a>Ошибка компилятора C2436

«Идентификатор»: функция-член или вложенный класс в списке инициализации конструктора

Не удается инициализировать функции-члены и локальные классы в списке инициализации конструктора.

Следующий пример приводит к возникновению ошибки C2436:

```
// C2436.cpp
struct S{
   int f();
   struct Inner{
      int i;
   };
   S():f(10), Inner(0){}   // C2436
};
```