---
title: Ошибка компилятора C2273
ms.date: 11/04/2016
f1_keywords:
- C2273
helpviewer_keywords:
- C2273
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
ms.openlocfilehash: f2ed5c49a9f8243fd5c9c302caf2876493c26bc3
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62388947"
---
# <a name="compiler-error-c2273"></a>Ошибка компилятора C2273

«Тип»: недопустимо в качестве правой части оператора «->»

Тип отображается как правый операнд `->` оператор.

Эта ошибка может быть вызвана пытается получить доступ к преобразования определяемого пользователем типа. Используйте ключевое слово `operator` между "->" и `type`.

Следующий пример приводит к возникновению ошибки C2273:

```
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