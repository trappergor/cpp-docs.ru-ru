---
title: Компилятор предупреждение (уровень 1) C4183
ms.date: 11/04/2016
f1_keywords:
- C4183
helpviewer_keywords:
- C4183
ms.assetid: dc48312c-4b34-44dd-80ff-eb5f11d5ca47
ms.openlocfilehash: 0d947a0f6d777a5ed3191d6d232a604028be2003
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50477458"
---
# <a name="compiler-warning-level-1-c4183"></a>Компилятор предупреждение (уровень 1) C4183

«Идентификатор»: отсутствие возвращаемого типа; предполагается, что функция-член, возвращающая «int»

Встроенное определение функции-члена в классе или структуре не имеет тип возвращаемого значения. Эта функция-член предполагается, что тип возвращаемого значения по умолчанию `int`.

Следующий пример приводит к возникновению ошибки C4183:

```
// C4183.cpp
// compile with: /W1 /c
#pragma warning(disable : 4430)
class MyClass1;
class MyClass2 {
   MyClass1() {};   // C4183
};
```