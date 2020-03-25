---
title: Ошибка компилятора C2555
ms.date: 11/04/2016
f1_keywords:
- C2555
helpviewer_keywords:
- C2555
ms.assetid: 5e49ebb8-7c90-457a-aa12-7ca7ab6574b2
ms.openlocfilehash: ebf3e4a3aff48311edd5fb95b01a7b2d23990231
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80202428"
---
# <a name="compiler-error-c2555"></a>Ошибка компилятора C2555

"Class1:: функция1": переопределяющий тип возвращаемого значения виртуальной функции отличается от "class2:: функция2", не является ковариантным

Виртуальная функция и производная переопределяемая функция имеют идентичные списки параметров, но различные типы возвращаемых значения. Переопределяющая функция в производном классе не может отличаться от виртуальной функции в базовом классе только его возвращаемым типом.

Чтобы устранить эту ошибку, приведите возвращаемое значение после вызова виртуальной функции.

Эта ошибка может также возникнуть при компиляции с помощью/CLR.   Например, визуальный C++ элемент, эквивалентный следующему C# объявлению:

```
Guid[] CheckSources(Guid sourceID, Guid[] carouselIDs);
```

— это

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
