---
title: Ошибка компилятора C3612
ms.date: 11/04/2016
f1_keywords:
- C3612
helpviewer_keywords:
- C3612
ms.assetid: aa6e3a2b-4afa-481c-98c1-1b6d1f82f869
ms.openlocfilehash: 499c31b0c02bd72695cd6118612609a70316f0ae
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755750"
---
# <a name="compiler-error-c3612"></a>Ошибка компилятора C3612

"тип": запечатанный класс не может быть абстрактным

Типы, определенные с помощью `value`, по умолчанию запечатаны, а класс является абстрактным, если только он не реализует все методы его базового класса. Запечатанный абстрактный класс не может быть базовым классом и не может быть создан.

Дополнительные сведения см. в статье [Классы и структуры](../../extensions/classes-and-structs-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3612:

```cpp
// C3612.cpp
// compile with: /clr /c
value struct V: public System::ICloneable {};   // C3612

// OK
value struct V2: public System::ICloneable {
   Object^ Clone();
};
```
