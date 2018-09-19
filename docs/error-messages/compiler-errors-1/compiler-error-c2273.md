---
title: Ошибка компилятора C2273 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2273
dev_langs:
- C++
helpviewer_keywords:
- C2273
ms.assetid: 3c682c66-97bf-4a23-a22c-d9a26a92bf95
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 995f75487820976d045e5db05fe2b170260240cc
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46066223"
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