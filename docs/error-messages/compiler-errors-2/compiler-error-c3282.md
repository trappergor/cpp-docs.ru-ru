---
title: Ошибка компилятора C3282
ms.date: 11/04/2016
f1_keywords:
- C3282
helpviewer_keywords:
- C3282
ms.assetid: bac2ac89-c360-4c24-bb81-c20c62ece9ba
ms.openlocfilehash: 7092ddc3bf6859212cbb143572de1ef3604a13d3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50491511"
---
# <a name="compiler-error-c3282"></a>Ошибка компилятора C3282

универсальный параметр, списки появляются только в управляемые или WinRTclasses, структурах или функциях

Список универсальных параметров был использован неправильно.  Дополнительные сведения см. в статье [Универсальные шаблоны](../../windows/generics-cpp-component-extensions.md).

## <a name="example"></a>Пример

В следующем примере показано возникновение ошибки C3282 и приводятся сведения по ее устранению.

```
// C3282.cpp
// compile with: /clr /c
generic <typename T> int x;   // C3282

ref struct GC0 {
   generic <typename T> int x;   // C3282
};

// OK
generic <typename T>
ref class M {};
```