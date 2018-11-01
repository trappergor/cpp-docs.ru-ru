---
title: Предупреждение компилятора (уровень 4) C4510
ms.date: 11/04/2016
f1_keywords:
- C4510
helpviewer_keywords:
- C4510
ms.assetid: fd28d1d4-ad27-4dad-94c0-9dba46c93180
ms.openlocfilehash: 80183e9f7ef17cbc37592f36eb8db1df2be94827
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50539065"
---
# <a name="compiler-warning-level-4-c4510"></a>Предупреждение компилятора (уровень 4) C4510

«класс»: не удалось создать конструктор по умолчанию

Компилятор не может создать конструктор по умолчанию для заданного класса и был создан без определенного пользователем конструктора. Вы не сможете создавать объекты этого типа.

Существует несколько ситуаций, в которых компилятор по умолчанию конструктор, включая:

- Константный член данных.

- Элемент данных, который является ссылкой.

Вам нужно создать конструктор по умолчанию, определяемые пользователем для класса, который инициализирует эти члены.

Следующий пример приводит к возникновению ошибки C4510:

```
// C4510.cpp
// compile with: /W4
struct A {
   const int i;
   int &j;
   A& operator=( const A& ); // C4510 expected
   // uncomment the following line to resolve this C4510
   // A(int ii, int &jj) : i(ii), j(jj) {}
};   // C4510

int main() {
}
```