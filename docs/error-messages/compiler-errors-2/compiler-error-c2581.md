---
title: Ошибка компилятора C2581
ms.date: 11/04/2016
f1_keywords:
- C2581
helpviewer_keywords:
- C2581
ms.assetid: 24a4e4c1-24d3-4e42-b760-7dcaf9740b16
ms.openlocfilehash: 03fc7e9da8a9b3a2e2c445f5b06395c2616f0d98
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74755438"
---
# <a name="compiler-error-c2581"></a>Ошибка компилятора C2581

"тип": статическая функция "operator =" недопустима

Оператор присваивания (`=`) неверно объявлен как `static`. Операторы присваивания не могут быть `static`ы. Дополнительные сведения см. в разделе [определяемые пользователем операторыC++(/CLI)](../../dotnet/user-defined-operators-cpp-cli.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C2581.

```cpp
// C2581.cpp
// compile with: /clr /c
ref struct Y {
   static Y ^ operator = (Y^ me, int i);   // C2581
   Y^ operator =(int i);   // OK
};
```
