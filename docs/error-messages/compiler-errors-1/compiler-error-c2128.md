---
title: Ошибка компилятора C2128
ms.date: 11/04/2016
f1_keywords:
- c2128
helpviewer_keywords:
- C2128
ms.assetid: 08cbf734-75b3-49f2-9026-9b319947612d
ms.openlocfilehash: 38cfb3ff81073a123f2d8c3c83c29c42c27d9dc7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225570"
---
# <a name="compiler-error-c2128"></a>Ошибка компилятора C2128

"функция": alloc_text/same_seg применимо только к функциям с компоновкой C

`#pragma alloc_text`может использоваться только с функциями, объявленными для использования компоновки C.

Следующий пример приводит к возникновению ошибки C2128:

```cpp
// C2128.cpp
// compile with: /c

// Delete the following line to resolve.
void func();
// #pragma alloc_text("my segment", func)   // C2128

extern "C" {
void func();
}

#pragma alloc_text("my segment", func)
void func() {}
```
