---
title: Ошибка компилятора C2109
ms.date: 11/04/2016
f1_keywords:
- C2109
helpviewer_keywords:
- C2109
ms.assetid: 2d1ac79d-a985-4904-a38b-b270578d664d
ms.openlocfilehash: 6592f36b29fe643e088669089b1af1b69b7b2125
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50452056"
---
# <a name="compiler-error-c2109"></a>Ошибка компилятора C2109

нижнего индекса требуется массив или указатель

Индекс использован с переменной, не являющейся массивом.

Следующий пример приводит к возникновению ошибки C2109:

```
// C2109.cpp
int main() {
   int a, b[10] = {0};
   a[0] = 1;   // C2109
   b[0] = 1;   // OK
}
```