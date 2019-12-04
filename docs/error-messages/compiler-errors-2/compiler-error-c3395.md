---
title: Ошибка компилятора C3395
ms.date: 11/04/2016
f1_keywords:
- C3395
helpviewer_keywords:
- C3395
ms.assetid: 26a9ebc9-ed97-47ce-b436-19aa2bcf6e50
ms.openlocfilehash: eaf63b42a6c44153a55d8aeb70f4f1174a5c895c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74737547"
---
# <a name="compiler-error-c3395"></a>Ошибка компилятора C3395

"функция": __declspec (dllexport) не может применяться к функции с соглашением о вызовах \__clrcall

`__declspec(dllexport)` и [__clrcall](../../cpp/clrcall.md) несовместимы.  Дополнительные сведения см. в статье [dllexport, dllimport](../../cpp/dllexport-dllimport.md).

Следующий пример приводит к возникновению ошибки C3395:

```cpp
// C3395.cpp
// compile with: /clr /c

__declspec(dllexport) void __clrcall Test(){}   // C3395
void __clrcall Test2(){}   // OK
__declspec(dllexport) void Test3(){}   // OK
```
