---
title: Ошибка компилятора C2555
ms.date: 11/04/2016
f1_keywords:
- C2555
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
ms.openlocfilehash: cc6c3a3a29665ccf65b77a3d9866986cb0a46b9e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62353232"
---
# <a name="compiler-error-c2555"></a>Ошибка компилятора C2555

«class1::function1»: переопределение виртуальной функции возвращают тип отличается и не является ковариантным «класс2::функция 2»

Виртуальная функция и производная переопределенной функции имеют идентичные списки параметров, кроме различные возвращаемые типы. Функцию переопределения в производном классе не может отличаться от виртуальной функции в базовом классе только типом возвращаемого.

Чтобы устранить эту ошибку, необходимо привести возвращаемое значение после вызова виртуальной функции.

Эта ошибка может также возникает при компиляции с параметром/CLR.   Например в Visual C++ эквивалентно следующее объявление C#:

```
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);
```

является

```
Guid CheckSources(Guid sourceID, Guid carouselIDs[]) [];
```

Следующий пример приводит к возникновению ошибки C2555:

```cpp
// C2555.cpp
// compile with: /c
struct X {
   virtual void func();
};
struct Y : X {
   char func();  // C2555
   void func2();   // OK
};
```