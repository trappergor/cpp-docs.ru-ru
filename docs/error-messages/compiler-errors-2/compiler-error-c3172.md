---
title: Ошибка компилятора C3172 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3172
dev_langs:
- C++
helpviewer_keywords:
- C3172
ms.assetid: 1834e2fd-6036-4c33-aff2-b51bc7c99441
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 25c3b1fd9132c6b170fdf74b1619a35d83959f90
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46117644"
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