---
title: Предупреждение компилятора (уровень 1) C4803
ms.date: 11/04/2016
f1_keywords:
- C4803
helpviewer_keywords:
- C4803
ms.assetid: 2552f3a6-c418-49f4-98a2-a929857be658
ms.openlocfilehash: bb8f5fe9d55a44193325a2fcfe9ef7675a2b3b89
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59779223"
---
# <a name="compiler-warning-level-1-c4803"></a>Предупреждение компилятора (уровень 1) C4803

«метод»: класс хранения, отличную от события, имеет метода raise «событие»

Событие методы должны иметь тот же класс хранения, что и объявление события. Компилятор корректирует методы события так, чтобы классы хранения совпадали.

Это предупреждение может возникнуть, если у вас есть класс, который реализует событие интерфейса. Компилятор не создает неявно метода raise для события в интерфейсе. При реализации этого интерфейса в классе, компилятор неявно создает метода raise, и этот метод не будет виртуальным, поэтому предупреждение. Дополнительные сведения о событиях см. в разделе [событий](../../extensions/event-cpp-component-extensions.md).

См. в разделе [предупреждение](../../preprocessor/warning.md) Дополнительные сведения о том, как отключить предупреждение.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4803.

```
// C4803.cpp
// compile with: /clr /W1
using namespace System;

public delegate void Del();

ref struct E {
   Del ^ _pd1;
   event Del ^ E1 {
      void add (Del ^ pd1) {
         _pd1 = dynamic_cast<Del ^>(Delegate::Combine(_pd1, pd1));
      }

      void remove(Del^ pd1) {
         _pd1 = dynamic_cast<Del^> (Delegate::Remove(_pd1, pd1));
      }

      virtual void raise() {   // C4803 warning (remove virtual)
         if (_pd1)
            _pd1();
      }
   }

   void func() {
      Console::WriteLine("In E::func()");
   }
};

int main() {
   E ^ ep = gcnew E;
   ep->E1 += gcnew Del(ep, &E::func);
   ep->E1();
   ep->E1 -= gcnew Del(ep, &E::func);
   ep->E1();
}
```
