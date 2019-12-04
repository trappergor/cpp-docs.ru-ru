---
title: Ошибка компилятора C3171
ms.date: 11/04/2016
f1_keywords:
- C3171
helpviewer_keywords:
- C3171
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
ms.openlocfilehash: a3af19fa6b4f4def9bb42325f648109cfafcdaef
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761755"
---
# <a name="compiler-error-c3171"></a>Ошибка компилятора C3171

"модуль": невозможно указать разные атрибуты модуля в проекте

атрибуты [модуля](../../windows/module-cpp.md) с различными списками параметров были найдены в двух файлах в компиляции. Для каждой компиляции можно указать только один уникальный атрибут `module`.

Идентичные `module` атрибуты могут быть указаны в нескольких файлах исходного кода.

Например, если найдены следующие атрибуты `module`:

```cpp
// C3171.cpp
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.0") ];
int main() {}
```

Затем:

```cpp
// C3171b.cpp
// compile with: C3171.cpp
// C3171 expected
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.1") ];
```

компилятор создаст C3171 (Обратите внимание на различные значения версии).
