---
title: Ошибка компилятора C3170
ms.date: 11/04/2016
f1_keywords:
- C3170
helpviewer_keywords:
- C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
ms.openlocfilehash: c4eb4a2551312791d05c8badb66af0070e74b630
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508327"
---
# <a name="compiler-error-c3170"></a>Ошибка компилятора C3170

в проекте не могут быть разные идентификаторы модулей

в двух файлах в компиляции обнаружены атрибуты [модуля](../../windows/attributes/module-cpp.md) с разными именами. `module`Для каждой компиляции можно указать только один уникальный атрибут.

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
