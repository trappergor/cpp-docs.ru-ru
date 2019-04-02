---
title: Ошибка компилятора C3282
ms.date: 11/04/2016
f1_keywords:
- C3282
helpviewer_keywords:
- C3282
ms.assetid: bac2ac89-c360-4c24-bb81-c20c62ece9ba
ms.openlocfilehash: 46be1f5250c1ca787909c48646d59180d62bd899
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58780851"
---
# <a name="compiler-error-c3282"></a>Ошибка компилятора C3282

универсальный параметр, списки появляются только в управляемые или WinRTclasses, структурах или функциях

Список универсальных параметров был использован неправильно.  Дополнительные сведения см. в статье [Универсальные шаблоны](../../extensions/generics-cpp-component-extensions.md).

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