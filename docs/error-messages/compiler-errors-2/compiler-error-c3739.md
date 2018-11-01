---
title: Ошибка компилятора C3739
ms.date: 11/04/2016
f1_keywords:
- C3739
helpviewer_keywords:
- C3739
ms.assetid: acffe894-08b8-4bf2-9249-9501e6e2bad3
ms.openlocfilehash: 34f035c089b183670e87a23eb62f995b2af23c9b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50567496"
---
# <a name="compiler-error-c3739"></a>Ошибка компилятора C3739

«класс»: синтаксис поддерживается только в том случае, если «layout_dependent» для event_receiver имеет значение true

Предпринята попытка подключить весь интерфейс событий, но `layout_dependent` на [event_receiver](../../windows/event-receiver.md) атрибут не имеет значение true; необходимо подключать одиночного события за раз.

Следующий пример приводит к возникновению ошибки C3739:

```
// C3739.cpp
struct A
{
   __event void e();
};

// event_receiver is implied
// [ event_receiver(layout_dependent=false)]

// use the following line instead
// [event_receiver(com, layout_dependent=true), coclass ]
struct B
{
   void f();
   B(A* a)
   {
      __hook(A, a, &B::f);   // C3739
      // use the following line instead to hook a single event
      // __hook(&A::e, a, &B::f);
   }
};

int main()
{
}
```