---
title: Ошибка компилятора C3737
ms.date: 11/04/2016
f1_keywords:
- C3737
helpviewer_keywords:
- C3737
ms.assetid: ca2aeb23-2491-4ccb-8838-884abf7065c8
ms.openlocfilehash: 6b61904fac09145ba749138a730603fcfdbb862d
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223386"
---
# <a name="compiler-error-c3737"></a>Ошибка компилятора C3737

"Delegate": делегат не может иметь явное соглашение о вызовах

Нельзя указать [соглашение о вызовах](../../cpp/calling-conventions.md) для **`delegate`** .

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3737:

```cpp
// C3737a.cpp
// compile with: /clr
delegate void __stdcall MyFunc();   // C3737
// Try the following line instead.
// delegate void MyFunc();

int main() {
}
```
