---
title: Предупреждение компилятора (уровень 1) C4461
ms.date: 11/04/2016
f1_keywords:
- C4461
helpviewer_keywords:
- C4461
ms.assetid: 104ffecc-3dd4-4cb1-89a8-81154fbe46d9
ms.openlocfilehash: 5cc9b08f0f25e9c92b4185f060ab123684c5d9e2
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50591026"
---
# <a name="compiler-warning-level-1-c4461"></a>Предупреждение компилятора (уровень 1) C4461

«Тип»: этот класс содержит метод завершения «метод_завершения», но нет деструктора «dtor»

Метод завершения в типе предполагает удаление ресурсов. Если метод завершения явно вызывается из деструктора типа, среда CLR определяет время запуска метода завершения, после объект выходит за пределы области.

Если определить деструктор в типе и явным образом вызывать метод завершения из деструктора, определенно можно использовать метод завершения.

Дополнительные сведения см. в разделе [деструкторы и методы завершения](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4461.

```
// C4461.cpp
// compile with: /W1 /clr /c
ref class A {
protected:
   !A() {}   // C4461
};

// OK
ref struct B {
   ~B() {
      B::!B();
   }

   !B() {}
};
```