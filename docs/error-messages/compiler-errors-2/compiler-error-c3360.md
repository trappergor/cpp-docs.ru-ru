---
title: Ошибка компилятора C3360
ms.date: 11/04/2016
f1_keywords:
- C3360
helpviewer_keywords:
- C3360
ms.assetid: 6acf983a-dbb6-422b-b045-a34bb4ba6761
ms.openlocfilehash: 785dbf3a96e97b68f2f8a5ede79ac8288eba4b21
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74757375"
---
# <a name="compiler-error-c3360"></a>Ошибка компилятора C3360

"строка": невозможно создать имя

Значение, переданное в атрибут [uuid](../../windows/uuid-cpp-attributes.md) , недопустимо.

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
