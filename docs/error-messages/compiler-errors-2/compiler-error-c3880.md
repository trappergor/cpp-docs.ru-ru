---
title: Ошибка компилятора C3880
ms.date: 11/04/2016
f1_keywords:
- C3880
helpviewer_keywords:
- C3880
ms.assetid: b0e05d1e-32d0-4034-9246-f37d23573ea9
ms.openlocfilehash: 54fd65fb4fe23a5c493a4e9ac83a5e44b0596362
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74736676"
---
# <a name="compiler-error-c3880"></a>Ошибка компилятора C3880

var: не может быть литеральным элементом данных

Тип [литерального](../../extensions/literal-cpp-component-extensions.md) атрибута должен быть или преобразован во время компиляции в один из следующих типов:

- целочисленный тип

- string

- перечисление с целочисленным или базовым типом

Следующий пример приводит к возникновению ошибки C3880:

```cpp
// C3880.cpp
// compile with: /clr /c
ref struct Y1 {
   literal System::Decimal staticConst1 = 10;   // C3880
   literal int staticConst2 = 10;   // OK
};
```
