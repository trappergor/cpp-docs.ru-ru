---
title: Ошибка компилятора C3172
ms.date: 11/04/2016
f1_keywords:
- C3172
helpviewer_keywords:
- C3172
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
ms.openlocfilehash: 1da2676d660d23e3fb71b56263779b1f1edacbf9
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74761742"
---
# <a name="compiler-error-c3172"></a>Ошибка компилятора C3172

"module_name": невозможно указать другие атрибуты idl_module в проекте

в двух файлах в компиляции были обнаружены [idl_module](../../windows/idl-module.md) атрибуты с одинаковыми именами, но разными параметрами `dllname` или `version`. Для каждой компиляции можно указать только один уникальный атрибут `idl_module`.

Идентичные `idl_module` атрибуты могут быть указаны в нескольких файлах исходного кода.

Например, если найдены следующие атрибуты `idl_module`:

```cpp
// C3172.cpp
[module(name="MyMod")];
[ idl_module(name="x", dllname="file.dll", version="1.1") ];
int main() {}
```

Затем:

```cpp
// C3172b.cpp
// compile with: C3172.cpp
// C3172 expected
[ idl_module(name="x", dllname="file.dll", version="1.0") ];
```

компилятор создаст C3172 (Обратите внимание на различные значения версии).
