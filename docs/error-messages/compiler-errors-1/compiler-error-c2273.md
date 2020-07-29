---
title: Ошибка компилятора C2273
ms.date: 11/04/2016
f1_keywords:
- C2273
helpviewer_keywords:
- C2273
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
ms.openlocfilehash: f5780c299eb4da03ece3611ee55062ee7ebcdaae
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87212791"
---
# <a name="compiler-error-c2273"></a>Ошибка компилятора C2273

"тип": недопустимо в качестве правой стороны оператора "->"

Тип отображается как правый операнд `->` оператора.

Эта ошибка может быть вызвана попыткой доступа к преобразованию определяемого пользователем типа. Используйте ключевое слово **`operator`** between-> и `type` .

Следующий пример приводит к возникновению ошибки C2273:

```cpp
// C2273.cpp
struct MyClass {
   operator int() {
      return 0;
   }
};
int main() {
   MyClass * ClassPtr = new MyClass;
   int i = ClassPtr->int();   // C2273
   int j = ClassPtr-> operator int();   // OK
}
```
