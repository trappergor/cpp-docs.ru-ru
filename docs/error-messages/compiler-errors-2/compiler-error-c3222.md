---
title: Ошибка компилятора C3222
ms.date: 11/04/2016
f1_keywords:
- C3222
helpviewer_keywords:
- C3222
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
ms.openlocfilehash: 96a6b1b81d2d82328dcb4ceaca376f247f785c13
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737950"
---
# <a name="compiler-error-c3222"></a>Ошибка компилятора C3222

"parameter": нельзя объявить аргументы по умолчанию для функций-членов управляемого типа, типа WinRT или универсальных функций

Запрещено объявлять параметр метода с аргументом по умолчанию. Перегруженные формы метода — один из способов решения этой проблемы. То есть вам нужно определить метод с тем же именем без параметров и затем инициализировать переменную в теле метода.

Следующий пример приводит к возникновению ошибки C3222:

```cpp
// C3222_2.cpp
// compile with: /clr
public ref class G {
   void f( int n = 0 );   // C3222
};
```
