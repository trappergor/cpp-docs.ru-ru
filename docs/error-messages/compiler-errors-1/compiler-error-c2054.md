---
title: Ошибка компилятора C2054
ms.date: 11/04/2016
f1_keywords:
- C2054
helpviewer_keywords:
- C2054
ms.assetid: 37f7c612-0d7d-4728-9e67-ac4160555f48
ms.openlocfilehash: 7366995f8930b4733ccff73aef38ebcf65a0c120
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62408775"
---
# <a name="compiler-error-c2054"></a>Ошибка компилятора C2054

Ожидалось "(" Выполнить "идентификатор"

Идентификатор функции используется в контексте, который должны следовать скобки.

Это ошибка может быть вызвана, опустив знак равенства (=) в сложных инициализации.

Следующий пример приводит к возникновению ошибки C2054:

```
// C2054.c
int array1[] { 1, 2, 3 };   // C2054, missing =
```

Возможное решение

```
// C2054b.c
int main() {
   int array2[] = { 1, 2, 3 };
}
```