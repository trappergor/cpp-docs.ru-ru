---
title: Предупреждение компилятора (уровень 1) C4488
ms.date: 11/04/2016
f1_keywords:
- C4488
helpviewer_keywords:
- C4488
ms.assetid: 55625e46-ddb5-4c7c-99c7-cd4aa9f879bd
ms.openlocfilehash: c816c1b3f5481ccff19fd2a2377c5fc98f950fee
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50577831"
---
# <a name="compiler-warning-level-1-c4488"></a>Предупреждение компилятора (уровень 1) C4488

«функция»: требуется ключевое слово «ключевое_слово» для реализации метода интерфейса «интерфейса»

Класс должен реализовывать все члены интерфейса, от которого он непосредственно наследуется. Реализуемый член должен быть открытым и должен быть помечен как virtual.

## <a name="example"></a>Пример

C4488 может произойти, если реализуемый член не является общим. Следующий пример приводит к возникновению ошибки C4488.

```
// C4488.cpp
// compile with: /clr /c /W1 /WX
interface struct MyI {
   void f1();
};

// implemented member not public
ref class B : MyI { virtual void f1() {} };  // C4488

// OK
ref class C : MyI {
public:
   virtual void f1() {}
};
```

## <a name="example"></a>Пример

C4488 может произойти, если реализуемый член не помечен как virtual. Следующий пример приводит к возникновению ошибки C4488.

```
// C4488_b.cpp
// compile with: /clr /c /W1 /WX
interface struct MyI {
   void f1();
};

ref struct B : MyI { void f1() {} };   // C4488
ref struct C : MyI { virtual void f1() {} };   // OK
```