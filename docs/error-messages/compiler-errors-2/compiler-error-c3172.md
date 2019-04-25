---
title: Ошибка компилятора C3172
ms.date: 11/04/2016
f1_keywords:
- C3172
helpviewer_keywords:
- C3172
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
ms.openlocfilehash: 5c9c1561b63c740b9f7f5d85b2bf3e04de2542c0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62175190"
---
# <a name="compiler-error-c3172"></a>Ошибка компилятора C3172

«module_name»: невозможно указать другие атрибуты idl_module в проекте

[idl_module](../../windows/idl-module.md) атрибуты с тем же имя, но разные `dllname` или `version` параметры обнаружены в двух файлах в компиляции. Только один уникальный `idl_module` атрибут может быть указан в одной компиляции.

Идентичные `idl_module` атрибуты могут быть заданы в более чем один файл исходного кода.

Например если следующее `idl_module` атрибуты обнаружены:

```
// C3172.cpp
[module(name="MyMod")];
[ idl_module(name="x", dllname="file.dll", version="1.1") ];
int main() {}
```

Затем:

```
// C3172b.cpp
// compile with: C3172.cpp
// C3172 expected
[ idl_module(name="x", dllname="file.dll", version="1.0") ];
```

компилятор создаст ошибку C3172 (Обратите внимание, значения разных версий).