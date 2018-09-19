---
title: Предупреждение компилятора (уровень 1) C4822 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4822
dev_langs:
- C++
helpviewer_keywords:
- C4822
ms.assetid: 0f231a30-2eb0-4722-aaa0-e2d19d3e7eea
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 33748a39eae4b6f2a84cadb818570f9a311b1fe1
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078326"
---
# <a name="compiler-warning-level-1-c4822"></a>Предупреждение компилятора (уровень 1) C4822

"член": функция-член локального класса не имеет тела

Функция-член локального класса объявлена в классе, но не определена в нем. Чтобы использовать функцию-член локального класса, необходимо определить ее внутри класса. Объявление функции в классе и определение функции за его пределами невозможно.

Любое определение функции-члена локального класса вне класса вызовет ошибку.

Следующий пример приводит к возникновению предупреждения C4822:

```
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