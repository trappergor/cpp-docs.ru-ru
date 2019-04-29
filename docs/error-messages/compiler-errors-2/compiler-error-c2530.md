---
title: Ошибка компилятора C2530
ms.date: 11/04/2016
f1_keywords:
- C2530
helpviewer_keywords:
- C2530
ms.assetid: b790a312-48df-4a6a-9e27-be2c5f32f16c
ms.openlocfilehash: 2c8164cad25d68ee61ff9fed7170482d5dfc9505
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62386997"
---
# <a name="compiler-error-c2530"></a>Ошибка компилятора C2530

«Идентификатор»: ссылки должны быть инициализированы

Необходимо инициализировать ссылку при ее объявлении, если она уже не объявлена:

- С помощью ключевого слова [extern](../../cpp/using-extern-to-specify-linkage.md).

- Как член класса, структуры или объединения (и он инициализируется в конструкторе).

- Как параметр в определении или объявлении функции.

- Как возвращаемый тип функции.

Следующий пример приводит к возникновению ошибки C2530:

```
// C2530.cpp
int main() {
   int i = 0;
   int &j;   // C2530
   int &k = i;   // OK
}
```