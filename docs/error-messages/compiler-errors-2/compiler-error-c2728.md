---
title: Ошибка компилятора C2728
ms.date: 11/04/2016
f1_keywords:
- C2728
helpviewer_keywords:
- C2728
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
ms.openlocfilehash: 3e3584d5e9166bb57e3be56e33f0198cacace7c1
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50615180"
---
# <a name="compiler-error-c2728"></a>Ошибка компилятора C2728

type: собственный массив не может содержать этот тип

Синтаксис для создания массива использовался для создания массива или управляемых объектов или объектов WinRT. Невозможно создать массив управляемых объектов или объектов WinRT, используя синтаксис управляемого массива.

Дополнительные сведения см. в описании [array](../../windows/arrays-cpp-component-extensions.md).

В следующем примере показано возникновение ошибки C2728 и приводятся сведения по ее устранению.

```
// C2728.cpp
// compile with: /clr

int main() {
   int^ arr[5];   // C2728

   // try the following line instead
   array<int>^arr2;
}
```
