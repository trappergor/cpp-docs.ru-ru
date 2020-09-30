---
title: Ошибка компилятора C3360
ms.date: 11/04/2016
f1_keywords:
- C3360
helpviewer_keywords:
- C3360
ms.assetid: 6acf983a-dbb6-422b-b045-a34bb4ba6761
ms.openlocfilehash: 5ac496d8ad981a8e36c7b69e73a42a1e1d2e214d
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91504700"
---
# <a name="compiler-error-c3360"></a>Ошибка компилятора C3360

"строка": невозможно создать имя

Значение, переданное в атрибут [uuid](../../windows/attributes/uuid-cpp-attributes.md) , недопустимо.

При компиляции следующего примера возникнет ошибка C3360:

```cpp
// C3360.cpp
[ uuid("1") ]
// try this line instead
// [ uuid("12341234-1234-1234-1234-123412341234") ]
struct A   // C3360
{
};

int main()
{
}
```
