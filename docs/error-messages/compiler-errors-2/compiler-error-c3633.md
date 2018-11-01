---
title: Ошибка компилятора C3633
ms.date: 11/04/2016
f1_keywords:
- C3633
helpviewer_keywords:
- C3633
ms.assetid: 7d65babf-2191-4d67-a69f-f5c4c2ddf946
ms.openlocfilehash: 2d96a0e4f5f0b34c76f41058316c7f158f1a939d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624100"
---
# <a name="compiler-error-c3633"></a>Ошибка компилятора C3633

Невозможно определить «член» в качестве члена управляемого «тип»

Члены данных среды CLR ссылочного класса не может иметь тип POD C++.  Можно создать только собственный тип POD в типе CLR.  Например тип POD не может содержать конструктор копии или оператор присваивания.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3633.

```
// C3633.cpp
// compile with: /clr /c
#pragma warning( disable : 4368 )

class A1 {
public:
   A1() { II = 0; }
   int II;
};

ref class B {
public:
   A1 a1;   // C3633
   A1 * a2;   // OK
   B() : a2( new A1 ) {}
    ~B() { delete a2; }
};
```
