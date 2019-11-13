---
title: Предупреждение компилятора (уровень 1) C4669
ms.date: 11/04/2016
f1_keywords:
- C4669
helpviewer_keywords:
- C4669
ms.assetid: 97730679-e3dc-44d4-b2a8-aa65badc17f2
ms.openlocfilehash: 58f7150caeb3e06ba400a08c6e484f677a8deff9
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051386"
---
# <a name="compiler-warning-level-1-c4669"></a>Предупреждение компилятора (уровень 1) C4669

cast: небезопасное преобразование: class является объектом управляемого типа или типа WinRT

Приведение содержит управляемый тип или тип среды выполнения Windows. Компилятор завершает приведение, выполняя побитовое копирование одного указателя в другой, но не выполняет другие проверки. Чтобы устранить это предупреждение, не преобразуйте классы, содержащие управляемые члены или типы среды выполнения Windows.

В следующем примере показано возникновение ошибки C4669 и приводятся сведения по ее устранению.

```cpp
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