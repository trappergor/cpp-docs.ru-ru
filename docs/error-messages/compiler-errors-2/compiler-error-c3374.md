---
title: Ошибка компилятора C3374
ms.date: 11/04/2016
f1_keywords:
- C3374
helpviewer_keywords:
- C3374
ms.assetid: 41431299-bd20-47d4-a0c8-1334dd79018b
ms.openlocfilehash: c9ee9130d77e844ab435ecc34dcf53e12449abba
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50474936"
---
# <a name="compiler-error-c3374"></a>Ошибка компилятора C3374

невозможно взять адрес 'функции' без создания экземпляра делегата

Адрес функции был взят в контексте, отличном от создания экземпляра делегата.

Следующий пример приводит к возникновению ошибки C3374:

```
// C3374.cpp
// compile with: /clr
public delegate void MyDel(int i);

ref class A {
public:
   void func1(int i) {
      System::Console::WriteLine("in func1 {0}", i);
   }
};

int main() {
   &A::func1;   // C3374

   // OK
   A ^ a = gcnew A;
   MyDel ^ StaticDelInst = gcnew MyDel(a, &A::func1);
}
```

## <a name="see-also"></a>См. также

[Практическое руководство. Определение и использование делегатов (C++/CLI)](../../dotnet/how-to-define-and-use-delegates-cpp-cli.md)