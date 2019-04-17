---
title: Ошибка компилятора C3896
ms.date: 11/04/2016
f1_keywords:
- C3896
helpviewer_keywords:
- C3896
ms.assetid: eb8be0f6-5b4e-4d71-8285-8a2a94f8ba29
ms.openlocfilehash: 00e103720dc666b17566b67da19d4e908bb3addd
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58767539"
---
# <a name="compiler-error-c3896"></a>Ошибка компилятора C3896

«член»: недопустимый инициализатор: этот член данных литерала можно инициализировать только с «nullptr»

Объект [литерала](../../extensions/literal-cpp-component-extensions.md) член данных инициализирован неправильно.  См. в разделе [nullptr](../../extensions/nullptr-cpp-component-extensions.md) Дополнительные сведения.

Следующий пример приводит к возникновению ошибки C3896:

```
// C3896.cpp
// compile with: /clr /c
ref class R{};

value class V {
   literal R ^ r = "test";   // C3896
   literal R ^ r2 = nullptr;   // OK
};
```