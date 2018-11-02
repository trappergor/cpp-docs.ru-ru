---
title: Ошибка компилятора C3126
ms.date: 11/04/2016
f1_keywords:
- C3126
helpviewer_keywords:
- C3126
ms.assetid: e72658a3-5d85-4a31-89a4-dbc3d475973d
ms.openlocfilehash: 92f01bd9a04d6350b348d734281855bb86b350d9
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50529718"
---
# <a name="compiler-error-c3126"></a>Ошибка компилятора C3126

Невозможно определить объединение «объединение» внутри управляемого типа «тип»

Объединение не может быть определен внутри управляемого типа.

Следующий пример приводит к возникновению ошибки C3126:

```
// C3126_2.cpp
// compile with: /clr /c
ref class Test
{
   union x
   {   // C3126
      int a;
      int b;
   };
};
```
