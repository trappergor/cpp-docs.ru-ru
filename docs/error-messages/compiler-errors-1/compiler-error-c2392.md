---
title: Ошибка компилятора C2392
ms.date: 11/04/2016
f1_keywords:
- C2392
helpviewer_keywords:
- C2392
ms.assetid: 98ced473-6383-46ed-b79c-21857d65dcb2
ms.openlocfilehash: 5977d9bf41d55ef6db8409e0187153fdbf91149e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491355"
---
# <a name="compiler-error-c2392"></a>Ошибка компилятора C2392

«метод1»: ковариантные возвращаемые типы не поддерживаются в управляемых или WinRTtypes, в противном случае «метод2» был бы переопределен

Ковариантные типы возвращаемого значения недопустимы для функций-членов среды выполнения Windows или при компиляции с параметром [/CLR (компиляция CLR)](../../build/reference/clr-common-language-runtime-compilation.md) параметр.

## <a name="example"></a>Пример

В следующем примере показано возникновение ошибки C2392 и приводятся сведения по ее устранению.

```
// C2392.cpp
// compile with: /clr
public ref struct B {
public:
   int i;
};

public ref struct D: public B{};

public ref struct B1 {
public:
   virtual B^ mf() {
      B^ pB = gcnew B;
      pB->i = 11;
      return pB;
   }
};

public ref struct D1: public B1 {
public:
   virtual D^ mf() override {  // C2392
   // try the following line instead
   // virtual B^ mf() override {
   // return type D^ is covariant with B^, not allowed with CLR types
      D^ pD = gcnew D;
      pD->i = 12;
      return pD;
   }
};

int main() {
   B1^ pB1 = gcnew D1;
   B^ pB = pB1->mf();
   D^ pD = dynamic_cast<D^>(pB);
}
```