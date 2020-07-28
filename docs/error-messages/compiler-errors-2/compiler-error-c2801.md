---
title: Ошибка компилятора C2801
ms.date: 11/04/2016
f1_keywords:
- C2801
helpviewer_keywords:
- C2801
ms.assetid: 35dfc7ea-9e37-4e30-baa1-944dc61302f5
ms.openlocfilehash: cfb89c79534318ab1fbcaa06667d594bfe2f1157
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214598"
---
# <a name="compiler-error-c2801"></a>Ошибка компилятора C2801

"operator оператор" должен быть не статическим членом

Следующие операторы можно перегружать только как нестатические члены:

- Сваивать`=`

- Доступ к членам класса`->`

- Перегрузке индексации`[]`

- Вызов функции`()`

Возможные причины C2801:

- Перегруженный оператор не является членом класса, структуры или объединения.

- Объявлен перегруженный оператор **`static`** .

- Следующий пример приводит к возникновению ошибки C2801:

```cpp
// C2801.cpp
// compile with: /c
operator[]();   // C2801 not a member
class A {
   static operator->();   // C2801 static
   operator()();   // OK
};
```
