---
title: Ошибка компилятора C3171
ms.date: 11/04/2016
f1_keywords:
- C3171
helpviewer_keywords:
- C3171
ms.assetid: 1ce26997-7ef1-4c9f-84da-003ea1a4251e
ms.openlocfilehash: 602c9ca1051646fca2c5788c036354047fad2522
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175443"
---
# <a name="compiler-error-c3171"></a>Ошибка компилятора C3171

«module»: невозможно указать другие атрибуты модуля в проекте

[модуль](../../windows/module-cpp.md) атрибуты с различными списками параметров были найдены в двух файлах в компиляции. Только один уникальный `module` атрибут может быть указан в одной компиляции.

Идентичные `module` атрибуты могут быть заданы в более чем один файл исходного кода.

Например если следующее `module` атрибуты обнаружены:

```
// C3171.cpp
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.0") ];
int main() {}
```

Затем:

```
// C3171b.cpp
// compile with: C3171.cpp
// C3171 expected
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f", version="1.1") ];
```

Компилятор сформировал бы C3171 (Обратите внимание, значения разных версий).