---
title: Ошибка компилятора C3895
ms.date: 11/04/2016
f1_keywords:
- C3895
helpviewer_keywords:
- C3895
ms.assetid: 771b9fe5-d6d4-4297-bf57-e2f857722155
ms.openlocfilehash: 633ffa86bce3579adb808dbba34127bb6f0665c9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749416"
---
# <a name="compiler-error-c3895"></a>Ошибка компилятора C3895

"var": элементы данных типа не могут быть "volatile"

Некоторые типы элементов данных, например [Literal](../../extensions/literal-cpp-component-extensions.md) или [initonly](../../dotnet/initonly-cpp-cli.md), не могут быть [временными](../../cpp/volatile-cpp.md).

Следующий пример приводит к возникновению ошибки C3895:

```cpp
// C3895.cpp
// compile with: /clr
ref struct Y1 {
   initonly
   volatile int data_var2;   // C3895
};
```
