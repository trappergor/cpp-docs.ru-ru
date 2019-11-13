---
title: Предупреждение компилятора (уровень 1) C4822
ms.date: 11/04/2016
f1_keywords:
- C4822
helpviewer_keywords:
- C4822
ms.assetid: 0f231a30-2eb0-4722-aaa0-e2d19d3e7eea
ms.openlocfilehash: f54f29fcbc6fb71033bc6d1d87c7ddb31622ee40
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051260"
---
# <a name="compiler-warning-level-1-c4822"></a>Предупреждение компилятора (уровень 1) C4822

"член": функция-член локального класса не имеет тела

Функция-член локального класса объявлена в классе, но не определена в нем. Чтобы использовать функцию-член локального класса, необходимо определить ее внутри класса. Объявление функции в классе и определение функции за его пределами невозможно.

Любое определение функции-члена локального класса вне класса вызовет ошибку.

Следующий пример приводит к возникновению предупреждения C4822:

```cpp
// C4822.cpp
// compile with: /W1
int main() {
   struct C {
      void func1(int);   // C4822
      // try the following line instead
      // void func1(int){}
  };
}
```