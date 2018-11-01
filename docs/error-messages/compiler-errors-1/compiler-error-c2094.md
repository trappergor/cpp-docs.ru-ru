---
title: Ошибка компилятора C2094
ms.date: 11/04/2016
f1_keywords:
- C2094
helpviewer_keywords:
- C2094
ms.assetid: 9e4f8f88-f189-46e7-91c9-481bacc7af87
ms.openlocfilehash: 072c51ca4ae25c6f51b1841ea129a7b4fb495bdf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529835"
---
# <a name="compiler-error-c2094"></a>Ошибка компилятора C2094

метка "идентификатор" не определена

Метка, используемая оператором [goto](../../cpp/goto-statement-cpp.md) , не существует в функции.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2094:

```cpp
// C2094.c
int main() {
   goto test;
}   // C2094
```

Возможное решение

```cpp
// C2094b.c
int main() {
   goto test;
   test:
   {
   }
}
```