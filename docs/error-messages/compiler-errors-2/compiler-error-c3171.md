---
title: Ошибка компилятора C3171
ms.date: 11/04/2016
f1_keywords:
- C3171
helpviewer_keywords:
- C3171
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
ms.openlocfilehash: 14f0cedc5448005a29d74f05ae3e68e74eb5cf1c
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91508305"
---
# <a name="compiler-error-c3171"></a>Ошибка компилятора C3171

"модуль": невозможно указать разные атрибуты модуля в проекте

атрибуты [модуля](../../windows/attributes/module-cpp.md) с различными списками параметров были найдены в двух файлах в компиляции. `module`Для каждой компиляции можно указать только один уникальный атрибут.

Идентичные `module` атрибуты могут быть указаны в нескольких файлах исходного кода.

Например, если `module` были найдены следующие атрибуты:

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
