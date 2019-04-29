---
title: Ошибка компилятора C2691
ms.date: 11/04/2016
f1_keywords:
- C2691
helpviewer_keywords:
- C2691
ms.assetid: 6925f8f3-ea60-4909-91e6-b781492c645d
ms.openlocfilehash: 34287b785532394d33e94e37e7a6a9955d935f14
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62360200"
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
