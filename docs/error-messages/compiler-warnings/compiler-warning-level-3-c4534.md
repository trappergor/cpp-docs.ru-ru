---
title: Предупреждение компилятора (уровень 3) C4534
ms.date: 11/04/2016
f1_keywords:
- c4534
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
ms.openlocfilehash: 2e617b18f2c7ed3b51d25eb44101629bbadcef9d
ms.sourcegitcommit: 217fac22604639ebd62d366a69e6071ad5b724ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/19/2019
ms.locfileid: "74189092"
---
# <a name="compiler-warning-level-3-c4534"></a>Предупреждение компилятора (уровень 3) C4534

"Конструктор" не будет конструктором по умолчанию для класса "класс" из-за аргумента по умолчанию

Неуправляемый класс может иметь конструктор с параметрами, имеющими значения по умолчанию, и компилятор будет использовать его в качестве конструктора по умолчанию. Класс, помеченный ключевым словом `value`, не будет использовать конструктор со значениями по умолчанию для его параметров в качестве конструктора по умолчанию.

Дополнительные сведения см. в статье [Классы и структуры](../../extensions/classes-and-structs-cpp-component-extensions.md).

Следующий пример приводит к возникновению ошибки C4534:

```cpp
// C4534.cpp
// compile with: /W3 /clr /WX
value class MyClass {
public:
   int ii;
   MyClass(int i = 9) {   // C4534, will not be the default constructor
      i++;
   }
};

int main() {
   MyClass ^ xx = gcnew MyClass;
   xx->ii = 0;
}
```