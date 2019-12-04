---
title: Ошибка компилятора C3179
ms.date: 11/04/2016
f1_keywords:
- C3179
helpviewer_keywords:
- C3179
ms.assetid: 60d7e41b-25fd-48ac-8b79-830c062f4dcd
ms.openlocfilehash: 330cc674f137e1d2718cf7535dbaffa96df01e8a
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761690"
---
# <a name="compiler-error-c3179"></a>Ошибка компилятора C3179

неименованный управляемый тип или тип WinRT не допускается

Все классы и структуры среды CLR и WinRT должны иметь имена.

В следующем примере показано возникновение ошибки C3179 и приводятся сведения по ее устранению.

```cpp
// C3179a.cpp
// compile with: /clr /c
typedef value struct { // C3179
// try the following line instead
// typedef value struct MyStruct {
   int i;
} V;
```
