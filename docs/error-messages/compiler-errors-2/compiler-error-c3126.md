---
title: Ошибка компилятора C3126
ms.date: 11/04/2016
f1_keywords:
- C3126
helpviewer_keywords:
- C3126
ms.assetid: e72658a3-5d85-4a31-89a4-dbc3d475973d
ms.openlocfilehash: 2b8901ce9914f35d4cd219f4d51477582fa676a8
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760729"
---
# <a name="compiler-error-c3126"></a>Ошибка компилятора C3126

невозможно определить объединение "Union" внутри управляемого типа "тип"

Объединение не может быть определено внутри управляемого типа.

Следующий пример приводит к возникновению ошибки C3126:

```cpp
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
