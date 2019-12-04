---
title: Ошибка компилятора C2133
ms.date: 11/04/2016
f1_keywords:
- C2133
helpviewer_keywords:
- C2133
ms.assetid: 8942f9e8-9818-468f-97db-09dbd124fcae
ms.openlocfilehash: b51b556ea576e02b85a5c2ee5032909af39c7b2f
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74758441"
---
# <a name="compiler-error-c2133"></a>Ошибка компилятора C2133

"идентификатор": неизвестный размер

Неразмерный массив объявляется как член класса, структуры, объединения или перечисления. Параметр/Za (ANSI C) не допускает неразмерных массивов элементов.

Следующий пример приводит к возникновению ошибки C2133:

```cpp
// C2133.cpp
// compile with: /Za
struct X {
   int a[0];   // C2133 unsized array
};
```

Возможное решение

```cpp
// C2133b.cpp
// compile with: /c
struct X {
   int a[0];   // no /Za
};
```
