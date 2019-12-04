---
title: Ошибка компилятора C2530
ms.date: 11/04/2016
f1_keywords:
- C2530
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
ms.openlocfilehash: 0816fcb4d9e2a3e6588dfcf937383fed7ab11395
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737131"
---
# <a name="compiler-error-c2530"></a>Ошибка компилятора C2530

"идентификатор": ссылки должны быть инициализированы

При объявлении ссылки необходимо инициализировать, если она уже не объявлена:

- С ключевым словом [extern](../../cpp/using-extern-to-specify-linkage.md).

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
