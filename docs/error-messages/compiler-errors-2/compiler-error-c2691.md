---
title: Ошибка компилятора C2691
ms.date: 11/04/2016
f1_keywords:
- C2691
helpviewer_keywords:
- C2691
ms.assetid: 6925f8f3-ea60-4909-91e6-b781492c645d
ms.openlocfilehash: 34287b785532394d33e94e37e7a6a9955d935f14
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50502002"
---
# <a name="compiler-error-c2691"></a>Ошибка компилятора C2691

«Тип данных»: управляемый или WinRTarray не может содержать элементы этого типа

Тип управляемого элемента массива или элемента массива WinRT может быть типом значения или ссылочным типом.

Следующий пример приводит к возникновению ошибки C2691:

```
// C2691a.cpp
// compile with: /clr
class A {};

int main() {
   array<A>^ a1 = gcnew array<A>(20);   // C2691
   array<int>^ a2 = gcnew array<int>(20);   // value type OK
}
```
