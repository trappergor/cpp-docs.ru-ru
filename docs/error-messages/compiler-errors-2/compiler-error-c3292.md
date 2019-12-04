---
title: Ошибка компилятора C3292
ms.date: 11/04/2016
f1_keywords:
- C3292
helpviewer_keywords:
- C3292
ms.assetid: ead485cc-5471-4e10-b361-300589ff5b70
ms.openlocfilehash: 566c92a5dc24c28b334653c6b5507b0bd9330992
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760131"
---
# <a name="compiler-error-c3292"></a>Ошибка компилятора C3292

пространство имен CLI нельзя открыть повторно

Пространство имен cli не может быть объявлено в вашем коде.  Дополнительные сведения см. в статье [Platform, default, and cli Namespaces (C++/CLI and C++/CX)](../../extensions/platform-default-and-cli-namespaces-cpp-component-extensions.md) (Пространства имен Platform, default и cli (C++/CLI и C++/CX)).

## <a name="example"></a>Пример

В следующем примере возникает ошибка C3292.

```cpp
// C3292.cpp
// compile with: /clr /c
namespace cli {};   // C3292
```
