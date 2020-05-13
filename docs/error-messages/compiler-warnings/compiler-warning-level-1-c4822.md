---
title: Предупреждение компилятора (уровень 1) C4822
ms.date: 11/04/2016
f1_keywords:
- C4822
helpviewer_keywords:
- C4822
ms.assetid: 0f231a30-2eb0-4722-aaa0-e2d19d3e7eea
ms.openlocfilehash: 59c42227c7e8be9bd31c37776d9724d23db61837
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174873"
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
