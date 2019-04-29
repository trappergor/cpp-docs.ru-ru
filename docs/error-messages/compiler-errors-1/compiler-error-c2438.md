---
title: Ошибка компилятора C2438
ms.date: 11/04/2016
f1_keywords:
- C2438
helpviewer_keywords:
- C2438
ms.assetid: 3a0ab3ba-d0e4-4d8f-971d-e503397cc827
ms.openlocfilehash: b2861090b5f7629c7f0cd94ea38a99e888909258
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62375760"
---
# <a name="compiler-error-c2438"></a>Ошибка компилятора C2438

«Идентификатор»: не удается инициализировать статические данные класса в конструктор

Конструктор используется для инициализации статических членов класса. Статические члены должны инициализироваться в определении вне объявления класса.

Следующий пример приводит к возникновению ошибки C2438:

```
// C2438.cpp
struct X {
   X(int i) : j(i) {}   // C2438
   static int j;
};

int X::j;

int main() {
   X::j = 1;
}
```