---
title: Ошибка компилятора C2005
ms.date: 11/04/2016
f1_keywords:
- C2005
helpviewer_keywords:
- C2005
ms.assetid: 090530ed-e0ec-4358-833a-ca24260e7ffe
ms.openlocfilehash: 49d0375d5733410d728797d2a881075377b33ba6
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50535542"
---
# <a name="compiler-error-c2005"></a>Ошибка компилятора C2005

\#строки требуется номер строки, найден «токен»

`#line` Должен располагаться после директивы с номером строки.

Следующий пример приводит к возникновению ошибки C2005:

```
// C2005.cpp
int main() {
   int i = 0;
   #line i   // C2005
}
```

Возможное решение

```
// C2005b.cpp
int main() {
   int i = 0;
   #line 0
}
```