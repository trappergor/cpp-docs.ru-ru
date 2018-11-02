---
title: Ошибка компилятора C3347
ms.date: 11/04/2016
f1_keywords:
- C3347
helpviewer_keywords:
- C3347
ms.assetid: e939ad29-0b78-4681-9618-9bdae5675cee
ms.openlocfilehash: 8b1c4ea76f65b9f07a96177d2e481d1abeba0927
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643114"
---
# <a name="compiler-error-c3347"></a>Ошибка компилятора C3347

"arg": обязательный аргумент не указан в атрибуте "idl_module"

Обязательный аргумент не передан в атрибут [idl_module](../../windows/idl-module.md) .

Следующий пример приводит к возникновению ошибки C3347:

```
// C3347.cpp
// compile with: /c
[module(name="xx")];

[idl_module(dllname="x")];    // C3347
// try the following line instead
// [idl_module(name="test", dllname="x")];
```