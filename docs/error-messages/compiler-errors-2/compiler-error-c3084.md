---
title: Ошибка компилятора C3084
ms.date: 11/04/2016
f1_keywords:
- C3084
helpviewer_keywords:
- C3084
ms.assetid: 0362cb70-e24e-476f-a24d-8f5bb97c3afd
ms.openlocfilehash: 337cd7f37bf94c7a3d5cffe6b167d4661e3b0a81
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74751460"
---
# <a name="compiler-error-c3084"></a>Ошибка компилятора C3084

"функция": метод завершения или деструктор не может быть "ключевое_слово"

Метод завершения или деструктор был объявлен неправильно.

Например, деструктор не следует помечать как запечатанный.  Деструктор будет недоступен для производных типов.  Дополнительные сведения см. в разделе [явные переопределения](../../extensions/explicit-overrides-cpp-component-extensions.md) и [деструкторы и методы завершения в статье как определить и использовать классы и структуры (C++/CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Пример

При компиляции следующего примера возникнет ошибка C3084.

```cpp
// C3084.cpp
// compile with: /clr /c
ref struct R {
protected:
   !R() sealed;   // C3084
   !R() abstract;   // C3084
   !R();
};
```
