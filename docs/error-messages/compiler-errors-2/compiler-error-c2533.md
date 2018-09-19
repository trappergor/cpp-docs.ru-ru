---
title: Ошибка компилятора C2533 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2533
dev_langs:
- C++
helpviewer_keywords:
- C2533
ms.assetid: 5b335652-076c-4824-87c8-a741f64a3ce0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 528b78e71713725907a9f0e2bd06cec1a8c62e67
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46045410"
---
# <a name="compiler-error-c2533"></a>Ошибка компилятора C2533

identifier: конструкторы не разрешены для типа возвращаемого значения

Конструктор класса не может иметь возвращаемый тип (даже тип `void`).

Типичной причиной возникновения этой ошибки является отсутствие точки с запятой между концом определения класса и первой реализацией конструктора. Компилятор считает класс определением возвращаемого типа для функции конструктора класса и вызывает ошибку C2533.

В следующем примере показано возникновение ошибки C2533 и приводятся сведения по ее устранению.

```
// C2533.cpp
// compile with: /c
class X {
public:
   X();
};

int X::X() {}   // C2533 - constructor return type not allowed
X::X() {}   // OK - fix by using no return type
```