---
title: Ошибка компилятора C3272 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3272
dev_langs:
- C++
helpviewer_keywords:
- C3272
ms.assetid: 7cdf254d-f207-4116-a1bf-7386f3b82a6f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: eaadad23d5647a0f27f4bbd9119c192f406da265
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46018571"
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
