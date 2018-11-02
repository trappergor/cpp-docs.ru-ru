---
title: Ошибка компилятора C2674
ms.date: 11/04/2016
f1_keywords:
- C2674
helpviewer_keywords:
- C2674
ms.assetid: 7cbd70d8-d992-44d7-a5cb-dd8cf9c759d2
ms.openlocfilehash: eb56651967f8fdc33b7c76b29883b25295d752d0
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50456814"
---
# <a name="compiler-error-c2674"></a>Ошибка компилятора C2674

универсальное объявление не допускается в этом контексте

Универсальный был объявлен неправильно. Дополнительные сведения см. в статье [Универсальные шаблоны](../../windows/generics-cpp-component-extensions.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2674.

```
// C2674.cpp
// compile with: /clr /c
void F(generic <class T> ref class R1);   // C2674
generic <class T> ref class R2 {};   // OK
```