---
title: Ошибка компилятора C3384
ms.date: 11/04/2016
f1_keywords:
- C3384
helpviewer_keywords:
- C3384
ms.assetid: c9f92c6a-62a9-4333-b2b1-bc55c7f288b6
ms.openlocfilehash: d1b7e1a69035df358cf84ad791f611928dab8b5a
ms.sourcegitcommit: 5cecccba0a96c1b4ccea1f7a1cfd91f259cc5bde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2019
ms.locfileid: "58773636"
---
# <a name="compiler-error-c3384"></a>Ошибка компилятора C3384

"параметр_типа": ограничение значения и ссылочное ограничение взаимно исключают друг друга

Невозможно ограничить универсальный тип до `value class` и `ref class`.

См. в разделе [ограничений для параметров универсального типа (C++выполняет)](../../extensions/constraints-on-generic-type-parameters-cpp-cli.md) Дополнительные сведения.

## <a name="example"></a>Пример

При компиляции следующего примера возникнет ошибка C3384.

```
// C3384.cpp
// compile with: /c /clr
generic <typename T>
where T : ref class
where T : value class   // C3384
ref class List {};
```