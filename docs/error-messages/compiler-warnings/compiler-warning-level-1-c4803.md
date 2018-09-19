---
title: Предупреждение компилятора (уровень 1) C4803 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4803
dev_langs:
- C++
helpviewer_keywords:
- C4803
ms.assetid: 2552f3a6-c418-49f4-98a2-a929857be658
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b4ea3eba61df387364b5103de19a28d88fe6e52a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46024831"
---
# <a name="compiler-warning-level-1-c4803"></a>Предупреждение компилятора (уровень 1) C4803

«метод»: класс хранения, отличную от события, имеет метода raise «событие»

Событие методы должны иметь тот же класс хранения, что и объявление события. Компилятор корректирует методы события так, чтобы классы хранения совпадали.

Это предупреждение может возникнуть, если у вас есть класс, который реализует событие интерфейса. Компилятор не создает неявно метода raise для события в интерфейсе. При реализации этого интерфейса в классе, компилятор неявно создает метода raise, и этот метод не будет виртуальным, поэтому предупреждение. Дополнительные сведения о событиях см. в разделе [событий](../../windows/event-cpp-component-extensions.md).

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
