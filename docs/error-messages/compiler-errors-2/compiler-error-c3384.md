---
title: Ошибка компилятора C3384
ms.date: 11/04/2016
f1_keywords:
- C3384
helpviewer_keywords:
- C3384
ms.assetid: c9f92c6a-62a9-4333-b2b1-bc55c7f288b6
ms.openlocfilehash: fdc129be94fce3f97eca988d8080e9d01fd48248
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87221098"
---
# <a name="compiler-error-c3384"></a>Ошибка компилятора C3384

"параметр_типа": ограничение значения и ссылочное ограничение взаимно исключают друг друга

Универсальный тип нельзя ограничить как для, так **`value class`** и для **`ref class`** .

Дополнительные сведения см. [в разделе ограничения для параметров универсального типа (C++/CLI)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) .

## <a name="example"></a>Пример

При компиляции следующего примера возникнет ошибка C3384.

```cpp
// C3384.cpp
// compile with: /c /clr
generic <typename T>
where T : ref class
where T : value class   // C3384
ref class List {};
```
