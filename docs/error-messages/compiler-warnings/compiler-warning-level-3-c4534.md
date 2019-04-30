---
title: Предупреждение компилятора (уровень 3) C4534
ms.date: 11/04/2016
f1_keywords:
- c4534
helpviewer_keywords:
- C4534
ms.assetid: ec2adf3b-d7a1-4005-bb0c-5d219df78dc8
ms.openlocfilehash: 81445ff42aca78a8e40e9c88eff4bb76a41a8669
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401882"
---
# <a name="compiler-warning-level-3-c4534"></a>Предупреждение компилятора (уровень 3) C4534

«конструктор» не будет конструктором по умолчанию для класса «class» из-за аргумента по умолчанию

Неуправляемый класс может иметь конструктор с параметрами, которые имеют значения по умолчанию, и компилятор будет использоваться как конструктор по умолчанию. Класс, помеченный `value` ключевое слово не будет использовать конструктор со значениями по умолчанию для его параметров как конструктор по умолчанию.

Дополнительные сведения см. в разделе [классы и структуры](../../extensions/classes-and-structs-cpp-component-extensions.md).

Следующий пример приводит к возникновению ошибки C4534:

```
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