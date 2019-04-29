---
title: Предупреждение компилятора C4694
ms.date: 10/25/2017
f1_keywords:
- C4694
helpviewer_keywords:
- C4694
ms.assetid: 5ca122bb-34f3-43ee-a21f-95802cd515f7
ms.openlocfilehash: 6164fd2e19e35233ba67feb84d117f1e4e01f20d
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62311056"
---
# <a name="compiler-warning-c4694"></a>Предупреждение компилятора C4694

> "*класс*": Запечатанный абстрактный класс не может иметь базового класса*base_class*"

Абстрактный и запечатанный класс не может наследовать от ссылочного типа; запечатанный и абстрактный класс не может ни реализовывать функции базового класса, ни разрешать использовать себя в качестве базового класса.

Дополнительные сведения см. в разделе [абстрактный](../../extensions/abstract-cpp-component-extensions.md), [запечатанный](../../extensions/sealed-cpp-component-extensions.md), и [классы и структуры](../../extensions/classes-and-structs-cpp-component-extensions.md).

Это предупреждение автоматически повышается до ошибки. Если вы хотите изменить это поведение, используйте [#pragma warning](../../preprocessor/warning.md).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4694.

```cpp
// C4694.cpp
// compile with: /c /clr
ref struct A {};
ref struct B sealed abstract : A {};   // C4694
```