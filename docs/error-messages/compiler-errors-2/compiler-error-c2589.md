---
title: Ошибка компилятора C2589 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2589
dev_langs:
- C++
helpviewer_keywords:
- C2589
ms.assetid: 1d7942c7-8a81-4bb4-b272-76a0019e8513
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 2db5dde898a3e5918eed62b2b32231b5d7ed014f
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46046060"
---
# <a name="compiler-error-c2589"></a>Ошибка компилятора C2589

«Идентификатор»: недопустимая лексема справа от "::"

Если класса, структуры или объединения имени отображается слева от оператора разрешения области действия (двойное двоеточие), маркер справа необходимо в том случае, класса, структуры или члена объединения. В противном случае любой глобальный идентификатор может появиться в правой части.

Оператор разрешения области действия не могут быть перегружены.

Следующий пример приводит к возникновению ошибки C2589:

```
// C2589.cpp
void Test(){}
class A {};
void operator :: ();   // C2589

int main() {
   ::Test();
}
```