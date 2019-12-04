---
title: Ошибка компилятора C3170
ms.date: 11/04/2016
f1_keywords:
- C3170
helpviewer_keywords:
- C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
ms.openlocfilehash: e2d74a637e2902fcf636b49068882f32aa706f94
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761768"
---
# <a name="compiler-error-c3170"></a>Ошибка компилятора C3170

в проекте не могут быть разные идентификаторы модулей

в двух файлах в компиляции обнаружены атрибуты [модуля](../../windows/module-cpp.md) с разными именами. Для каждой компиляции можно указать только один уникальный атрибут `module`.

Идентичные `module` атрибуты могут быть указаны в нескольких файлах исходного кода.

Например, если найдены следующие атрибуты модуля:

```cpp
// C3170.cpp
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];
int main() {}
```

Затем:

```cpp
// C3170b.cpp
// compile with: C3170.cpp
// C3170 expected
[ module(name="MyModule1", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];
```

компилятор создаст C3170 (Обратите внимание на различные имена).
