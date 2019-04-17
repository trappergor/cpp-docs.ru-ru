---
title: Ошибка компилятора C2728
ms.date: 11/04/2016
f1_keywords:
- C2728
helpviewer_keywords:
- C2728
ms.assetid: 65635f91-1cd1-46e4-9ad7-14726d0546af
ms.openlocfilehash: 1fbbc3d63386ebe98a447de8b7166a5263d2168f
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58767422"
---
# <a name="compiler-error-c2728"></a>Ошибка компилятора C2728

type: собственный массив не может содержать этот тип

Синтаксис для создания массива использовался для создания массива или управляемых объектов или объектов WinRT. Невозможно создать массив управляемых объектов или объектов WinRT, используя синтаксис управляемого массива.

Дополнительные сведения см. в описании [array](../../extensions/arrays-cpp-component-extensions.md).

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
