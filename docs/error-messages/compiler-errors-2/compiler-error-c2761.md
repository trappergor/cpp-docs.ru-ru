---
title: Ошибка компилятора C2761
ms.date: 11/04/2016
f1_keywords:
- C2761
helpviewer_keywords:
- C2761
ms.assetid: 38c79a05-b56d-485b-820f-95e8c0cb926f
ms.openlocfilehash: 7493934879068109c582a85592f485c1d391e2de
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90743390"
---
# <a name="compiler-error-c2761"></a>Ошибка компилятора C2761

"функция": повторное объявление функции члена не разрешено

Нельзя повторно объявить функцию-член. Его можно определить, но не объявлять повторно.

## <a name="examples"></a>Примеры

Следующий пример приводит к возникновению ошибки C2761.

```cpp
// C2761.cpp
class a {
   int t;
   void test();
};

void a::a;     // C2761
void a::test;  // C2761
```

Невозможно определить нестатические члены класса или структуры.  Следующий пример приводит к возникновению ошибки C2761.

```cpp
// C2761_b.cpp
// compile with: /c
struct C {
   int s;
   static int t;
};

int C::s;   // C2761
int C::t;   // OK
```
