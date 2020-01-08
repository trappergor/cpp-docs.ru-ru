---
title: Ошибка компилятора C2063
ms.date: 11/04/2016
f1_keywords:
- C2063
helpviewer_keywords:
- C2063
ms.assetid: 0a90c18f-4029-416a-9128-e8713b53e6f1
ms.openlocfilehash: 91acddd812a3caf9c16a4d1d4f92315045eae7da
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75302020"
---
# <a name="compiler-error-c2063"></a>Ошибка компилятора C2063

"идентификатор": не является функцией

Идентификатор используется в качестве функции, но не объявлен как функция.

Следующий пример приводит к возникновению ошибки C2063:

```c
// C2063.c
int main() {
   int i, j;
   j = i();    // C2063, i is not a function
}
```

Возможное решение:

```c
// C2063b.c
int i() { return 0;}
int main() {
   int j;
   j = i();
}
```
