---
title: Ошибка компилятора C3170 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3170
dev_langs:
- C++
helpviewer_keywords:
- C3170
ms.assetid: ca9a59d6-7df3-42f0-b028-c09d0af3ac2a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e7a193abcd59c3e9454eec1108f1e3bbb66efcc8
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46070370"
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