---
title: Ошибка компилятора C2701
ms.date: 11/04/2016
f1_keywords:
- C2701
helpviewer_keywords:
- C2701
ms.assetid: 31cf2ab7-ced9-4f75-aa51-e169e20407fb
ms.openlocfilehash: b16ddb16d98a81e53b29ff51e41d19073200a2e5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62161294"
---
# <a name="compiler-error-c2701"></a>Ошибка компилятора C2701

«функция»: шаблон функции не может быть дружественным локального класса

Функция шаблона не может быть дружественная функция локального класса.

Следующий пример приводит к возникновению ошибки C2701:

```
// C2701.cpp
// compile with: /c
template<typename T>   // OK
void f1(const T &);

void MyFunction() {
   class MyClass {
      template<typename T> friend void f2(const T &);   // C2701
   };
}
```