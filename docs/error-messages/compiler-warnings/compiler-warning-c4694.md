---
title: Предупреждение компилятора C4694
ms.date: 10/25/2017
f1_keywords:
- C4694
helpviewer_keywords:
- C4694
ms.assetid: 5ca122bb-34f3-43ee-a21f-95802cd515f7
ms.openlocfilehash: daf5423588d08260239c3cff5a68532a358d07b2
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80165123"
---
# <a name="compiler-warning-c4694"></a>Предупреждение компилятора C4694

> "*класс*": запечатанный абстрактный класс не может иметь базовый класс "*base_class*"

Абстрактный и запечатанный класс не может наследовать от ссылочного типа; запечатанный и абстрактный класс не может ни реализовывать функции базового класса, ни разрешать использовать себя в качестве базового класса.

Дополнительные сведения см. в разделе [абстрактные](../../extensions/abstract-cpp-component-extensions.md), [запечатанные](../../extensions/sealed-cpp-component-extensions.md) [классы и структуры](../../extensions/classes-and-structs-cpp-component-extensions.md).

Это предупреждение автоматически повышается до ошибки. Если вы хотите изменить это поведение, используйте [#pragma предупреждение](../../preprocessor/warning.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4694.

```cpp
// C4694.cpp
// compile with: /c /clr
ref struct A {};
ref struct B sealed abstract : A {};   // C4694
```
