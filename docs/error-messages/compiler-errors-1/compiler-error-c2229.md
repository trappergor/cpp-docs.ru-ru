---
title: Ошибка компилятора C2229
ms.date: 11/04/2016
f1_keywords:
- C2229
helpviewer_keywords:
- C2229
ms.assetid: 933c7cf2-a463-4e74-b0b4-59dedad987fb
ms.openlocfilehash: 998067e9af178c1898c3443c4e84da965c22fa81
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62301738"
---
# <a name="compiler-error-c2229"></a>Ошибка компилятора C2229

тип «идентификатор» имеет недопустимый массив нулевого размера

Член структуры или битовое поле содержит массив нулевого размера, который не последнего члена.

Поскольку может иметь массив нулевого размера в качестве последнего члена структуры, необходимо указать его размер при распределении структуры.

Если массив нулевого размера не последнего члена структуры, компилятор не может вычислить смещение для оставшихся полей.

Следующий пример приводит к возникновению ошибки C2229:

```
// C2229.cpp
struct S {
   int a[0];  // C2229  zero-sized array
   int b[1];
};

struct S2 {
   int a;
   int b[0];
};

int main() {
   // allocate 7 elements for b field
   S2* s2 = (S2*)new int[sizeof(S2) + 7*sizeof(int)];
   s2->b[6] = 100;
}
```