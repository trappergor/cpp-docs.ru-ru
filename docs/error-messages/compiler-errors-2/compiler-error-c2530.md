---
title: Ошибка компилятора C2530
ms.date: 11/04/2016
f1_keywords:
- C2530
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
ms.openlocfilehash: 4eca5579f6bf132452a813d8dd99193df5f76b92
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91500539"
---
# <a name="compiler-error-c2530"></a>Ошибка компилятора C2530

"идентификатор": ссылки должны быть инициализированы

При объявлении ссылки необходимо инициализировать, если она уже не объявлена:

- С ключевым словом [extern](../../cpp/extern-cpp.md).

- В качестве члена класса, структуры или объединения (и инициализируется в конструкторе).

- В качестве параметра в объявлении или определении функции.

- В качестве возвращаемого типа функции.

Следующий пример приводит к возникновению ошибки C2530:

```cpp
// C2530.cpp
int main() {
   int i = 0;
   int &j;   // C2530
   int &k = i;   // OK
}
```
