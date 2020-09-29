---
title: Ошибка компилятора C3739
ms.date: 11/04/2016
f1_keywords:
- C3739
helpviewer_keywords:
- C3739
ms.assetid: acffe894-08b8-4bf2-9249-9501e6e2bad3
ms.openlocfilehash: 7235d86ed00663b81aaddb87fdeae957c0f73053
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500428"
---
# <a name="compiler-error-c3739"></a>Ошибка компилятора C3739

"класс": синтаксис поддерживается только в том случае, если параметр "layout_dependent" event_receiver имеет значение true

Вы попытались подключить весь интерфейс событий, но `layout_dependent` на [event_receiver](../../windows/attributes/event-receiver.md) атрибут не имеет значения true; необходимо одновременно присоединить одно событие.

Следующий пример приводит к возникновению ошибки C3739:

```cpp
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
