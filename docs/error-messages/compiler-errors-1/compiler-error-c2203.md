---
title: Ошибка компилятора C2203
ms.date: 11/04/2016
f1_keywords:
- C2203
helpviewer_keywords:
- C2203
ms.assetid: 5497df43-86f6-43d5-b6cb-723c4c589b10
ms.openlocfilehash: 848fdad460402238f4957344dd49bd9128352b4c
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383274"
---
# <a name="compiler-error-c2203"></a>Ошибка компилятора C2203

Удалите оператор нельзя указывать границы для массива

С помощью **/Za** параметр (ANSI), `delete` оператор можно удалить полный массив, но не частей или конкретные члены массива.

Следующий пример приводит к возникновению ошибки C2203:

```
// C2203.cpp
// compile with: /Za
int main() {
   int *ar = new int[10];
   delete [4] ar;   // C2203
   // try the following line instead
   // delete [] ar;
}
```