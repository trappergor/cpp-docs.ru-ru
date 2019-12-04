---
title: Ошибка компилятора C3898
ms.date: 11/04/2016
f1_keywords:
- C3898
helpviewer_keywords:
- C3898
ms.assetid: d9a90df6-87e4-4fe7-ab01-c226ee86bf10
ms.openlocfilehash: 02c649fb906b0c5f09afe25952a8670c1a0e7f3d
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749208"
---
# <a name="compiler-error-c3898"></a>Ошибка компилятора C3898

"var": элементы данных типа могут быть только членами управляемых типов

Элемент данных [initonly](../../dotnet/initonly-cpp-cli.md) был объявлен в собственном классе.  Элемент данных `initonly` может быть объявлен только в классе CLR.

Следующий пример приводит к возникновению ошибки C3898:

```cpp
// C3898.cpp
// compile with: /clr
struct Y1 {
   initonly
   static int data_var = 9;   // C3898
};
```

Возможное решение

```cpp
// C3898b.cpp
// compile with: /clr /c
ref struct Y1 {
   initonly
   static int data_var = 9;
};
```
