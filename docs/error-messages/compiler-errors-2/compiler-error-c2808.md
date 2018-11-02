---
title: Ошибка компилятора C2808
ms.date: 11/04/2016
f1_keywords:
- C2808
helpviewer_keywords:
- C2808
ms.assetid: 3d745102-d3b3-4735-a7d2-ad42d5bf3cfa
ms.openlocfilehash: 7b40a81748748a7566a8c1e6add84121f8925895
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50572023"
---
# <a name="compiler-error-c2808"></a>Ошибка компилятора C2808

унарный оператор «оператор» имеет слишком много формальных параметров

Унарный оператор имеет недействительный список параметров.

Следующий пример приводит к возникновению ошибки C2808:

```
// C2808.cpp
// compile with: /c
class X {
public:
   X operator! ( X );   // C2808 nonvoid parameter list
   X operator! ( void );   // OK
};

```