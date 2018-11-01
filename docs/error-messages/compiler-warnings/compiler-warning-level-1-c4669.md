---
title: Предупреждение компилятора (уровень 1) C4669
ms.date: 11/04/2016
f1_keywords:
- C4669
helpviewer_keywords:
- C4669
ms.assetid: 97730679-e3dc-44d4-b2a8-aa65badc17f2
ms.openlocfilehash: f4d0b87c91649c5f2f6b5823fea82d2ce355d11a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50518642"
---
# <a name="compiler-warning-level-1-c4669"></a>Предупреждение компилятора (уровень 1) C4669

cast: небезопасное преобразование: class является объектом управляемого типа или типа WinRT

Приведение содержит управляемый тип или тип среды выполнения Windows. Компилятор завершает приведение, выполняя побитовое копирование одного указателя в другой, но не выполняет другие проверки. Чтобы устранить это предупреждение, не преобразуйте классы, содержащие управляемые члены или типы среды выполнения Windows.

В следующем примере показано возникновение ошибки C4669 и приводятся сведения по ее устранению.

```
// C4669.cpp
// compile with: /clr /W1
ref struct A {
   int i;
   Object ^ pObj;   // remove the managed member to fix the warning
};

ref struct B {
   int j;
};

int main() {
   A ^ a = gcnew A;
   B ^ b = reinterpret_cast<B ^>(a);   // C4669
}
```