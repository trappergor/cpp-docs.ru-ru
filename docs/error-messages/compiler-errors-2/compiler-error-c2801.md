---
title: Ошибка компилятора C2801
ms.date: 11/04/2016
f1_keywords:
- C2801
helpviewer_keywords:
- C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
ms.openlocfilehash: 44f7988f9fedb882972b2823f2fe70d9512d4e87
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50484790"
---
# <a name="compiler-error-c2801"></a>Ошибка компилятора C2801

«оператор» должен быть статическим членом

Следующие операторы могут перегружаться только как нестатические члены:

- Назначение `=`

- Доступ к членам класса `->`

- Подписи пропущена `[]`

- Вызов функции `()`

Возможные причины C2801:

- Перегруженный оператор не класса, структуры или члена объединения.

- Перегруженный оператор объявлен `static`.

- Следующий пример приводит к возникновению ошибки C2801:

```
// C2801.cpp
// compile with: /c
operator[]();   // C2801 not a member
class A {
   static operator->();   // C2801 static
   operator()();   // OK
};
```