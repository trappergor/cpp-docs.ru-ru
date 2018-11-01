---
title: Ошибка компилятора C3222
ms.date: 11/04/2016
f1_keywords:
- C3222
helpviewer_keywords:
- C3222
ms.assetid: 5624bde8-2fd0-4b8b-92ce-5dfbaf91cf93
ms.openlocfilehash: 9f2c245e98609c8da8f5f89902d5c51bbf9d2b4f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50638676"
---
# <a name="compiler-error-c3222"></a>Ошибка компилятора C3222

"parameter": нельзя объявить аргументы по умолчанию для функций-членов управляемого типа, типа WinRT или универсальных функций

Запрещено объявлять параметр метода с аргументом по умолчанию. Перегруженные формы метода — один из способов решения этой проблемы. То есть вам нужно определить метод с тем же именем без параметров и затем инициализировать переменную в теле метода.

Следующий пример приводит к возникновению ошибки C3222:

```
// C3222_2.cpp
// compile with: /clr
public ref class G {
   void f( int n = 0 );   // C3222
};
```
