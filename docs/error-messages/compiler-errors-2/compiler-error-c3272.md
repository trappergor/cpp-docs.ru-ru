---
title: Ошибка компилятора C3272
ms.date: 11/04/2016
f1_keywords:
- C3272
helpviewer_keywords:
- C3272
ms.assetid: 7cdf254d-f207-4116-a1bf-7386f3b82a6f
ms.openlocfilehash: 3e4348dcce0cfd04234b515877d788e5330f8e4c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50598579"
---
# <a name="compiler-error-c3272"></a>Ошибка компилятора C3272

"символ": символу требуется атрибут FieldOffset, так как он является членом "имя типа", определенным с помощью StructLayout(LayoutKind::Explicit)

При использовании атрибута `StructLayout(LayoutKind::Explicit)` необходимо помечать поля с помощью атрибута `FieldOffset`.

Следующий пример приводит к возникновению ошибки C3272:

```
// C3272_2.cpp
// compile with: /clr /c
using namespace System;
using namespace System::Runtime::InteropServices;

[StructLayout(LayoutKind::Explicit)]
ref struct X
{
   int data_;   // C3272
   // try the following line instead
   // [FieldOffset(0)] int data_;
};
```
