---
title: Ошибка компилятора C3880
ms.date: 11/04/2016
f1_keywords:
- C3880
helpviewer_keywords:
- C3880
ms.assetid: b0e05d1e-32d0-4034-9246-f37d23573ea9
ms.openlocfilehash: 0b169309db88291f8a83b6d1192787b6396e84a5
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62338471"
---
# <a name="compiler-error-c3880"></a>Ошибка компилятора C3880

«var»: не может быть данными-членом литерала

Тип [литерала](../../extensions/literal-cpp-component-extensions.md) должен быть атрибут, или во время компиляции можно преобразовать в один из следующих типов:

- целочисленный тип

- string

- Перечисление с целым или базовым типом

Следующий пример приводит к возникновению ошибки C3880:

```
// C3880.cpp
// compile with: /clr /c
ref struct Y1 {
   literal System::Decimal staticConst1 = 10;   // C3880
   literal int staticConst2 = 10;   // OK
};
```