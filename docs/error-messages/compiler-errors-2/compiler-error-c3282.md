---
title: Ошибка компилятора C3282
ms.date: 11/04/2016
f1_keywords:
- C3282
helpviewer_keywords:
- C3282
ms.assetid: bac2ac89-c360-4c24-bb81-c20c62ece9ba
ms.openlocfilehash: a119f8a9482d3f49c98873fee6f54b434416ee48
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757583"
---
# <a name="compiler-error-c3282"></a>Ошибка компилятора C3282

Списки универсальных параметров могут использоваться только в управляемых или Винртклассес, структурах и функциях

Список универсальных параметров был использован неправильно.  Дополнительные сведения см. в статье [Универсальные шаблоны](../../extensions/generics-cpp-component-extensions.md).

## <a name="example"></a>Пример

В следующем примере показано возникновение ошибки C3282 и приводятся сведения по ее устранению.

```cpp
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
