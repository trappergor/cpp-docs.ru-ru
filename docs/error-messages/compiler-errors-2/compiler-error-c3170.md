---
title: Ошибка компилятора C3170
ms.date: 11/04/2016
f1_keywords:
- C3170
helpviewer_keywords:
- C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
ms.openlocfilehash: 5ef39e4580601dd90b5695d9115902bb5b834409
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62174709"
---
# <a name="compiler-error-c3170"></a>Ошибка компилятора C3170

в проекте не может быть разных идентификаторов модулей

[модуль](../../windows/module-cpp.md) атрибуты с разными именами были найдены в двух файлах в компиляции. Только один уникальный `module` атрибут может быть указан в одной компиляции.

Идентичные `module` атрибуты могут быть заданы в более чем один файл исходного кода.

Например, если найдены следующие атрибуты модуля:

```
// C3170.cpp
[ module(name="MyModule", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];
int main() {}
```

Затем:

```
// C3170b.cpp
// compile with: C3170.cpp
// C3170 expected
[ module(name="MyModule1", uuid="373a1a4e-469b-11d3-a6b0-00c04f79ae8f") ];
```

компилятор выдаст ошибку C3170 (Обратите внимание, разные имена).