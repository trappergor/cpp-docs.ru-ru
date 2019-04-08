---
title: Ошибка компилятора C3084
ms.date: 11/04/2016
f1_keywords:
- C3084
helpviewer_keywords:
- C3084
ms.assetid: 0362cb70-e24e-476f-a24d-8f5bb97c3afd
ms.openlocfilehash: 01e229fe0ae5bf9e04c577bb653ff1ed7fdb33bf
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "58773910"
---
# <a name="compiler-error-c3084"></a>Ошибка компилятора C3084

"функция": метод завершения или деструктор не может быть "ключевое_слово"

Метод завершения или деструктор был объявлен неправильно.

Например, деструктор не следует помечать как запечатанный.  Деструктор будет недоступен для производных типов.  Дополнительные сведения см. в разделе [явное переопределение](../../extensions/explicit-overrides-cpp-component-extensions.md) и [деструкторы и методы завершения в разделе: Определение и использование классов и структур (C + +/ CLI)](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

## <a name="example"></a>Пример

При компиляции следующего примера возникнет ошибка C3084.

```
// C3084.cpp
// compile with: /clr /c
ref struct R {
protected:
   !R() sealed;   // C3084
   !R() abstract;   // C3084
   !R();
};
```