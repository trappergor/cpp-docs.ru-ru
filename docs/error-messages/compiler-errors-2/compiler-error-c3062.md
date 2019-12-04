---
title: Ошибка компилятора C3062
ms.date: 11/04/2016
f1_keywords:
- C3062
helpviewer_keywords:
- C3062
ms.assetid: 78632e6d-255f-42c3-b124-31a9194ff86d
ms.openlocfilehash: 9b1fbc8f4ca2ce3434a30e833f4741bc17015bbb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74749533"
---
# <a name="compiler-error-c3062"></a>Ошибка компилятора C3062

"enum": для перечислителя требуется значение, так как базовый тип — "тип"

Для перечисления можно указать базовый тип. Однако для некоторых типов требуется назначить значения каждому перечислителю.

Дополнительные сведения о перечислениях см. в разделе [Класс Enum](../../extensions/enum-class-cpp-component-extensions.md).

Следующий пример приводит к возникновению ошибки C3062:

```cpp
// C3062.cpp
// compile with: /clr

enum class MyEnum : bool { a };   // C3062
enum class MyEnum2 : bool { a = true};   // OK
```
