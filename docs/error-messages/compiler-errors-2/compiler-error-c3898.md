---
title: Ошибка компилятора C3898
ms.date: 11/04/2016
f1_keywords:
- C3898
helpviewer_keywords:
- C3898
ms.assetid: d9a90df6-87e4-4fe7-ab01-c226ee86bf10
ms.openlocfilehash: 503f295d62c598e3138b1a001d6b350c0d90ea84
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50549739"
---
# <a name="compiler-error-c3898"></a>Ошибка компилятора C3898

«var»: элементы данных типа может быть только членами управляемых типов

[Initonly](../../dotnet/initonly-cpp-cli.md) данные-член, объявленный в собственный класс.  `initonly` Элемент данных могут объявляться только в классе CLR.

Следующий пример приводит к возникновению ошибки C3898:

```
// C3898.cpp
// compile with: /clr
struct Y1 {
   initonly
   static int data_var = 9;   // C3898
};
```

Возможное решение

```
// C3898b.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int data_var = 9;
};
```