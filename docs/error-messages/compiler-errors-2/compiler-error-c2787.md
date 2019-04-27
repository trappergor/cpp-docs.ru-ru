---
title: Ошибка компилятора C2787
ms.date: 11/04/2016
f1_keywords:
- C2787
helpviewer_keywords:
- C2787
ms.assetid: 34cb57e6-cafe-4ce7-bcc6-53d194629bd0
ms.openlocfilehash: 656fcd8a1a0429546189de8c3f01ab928c6333ae
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62256871"
---
# <a name="compiler-error-c2787"></a>Ошибка компилятора C2787

«Идентификатор»: идентификатор GUID не была связана с этим объектом

[__Uuidof](../../cpp/uuidof-operator.md) оператор принимает определяемого пользователем типа с присоединенным идентификатором GUID или объект такого типа определяемых пользователем. Эта ошибка возникает, если аргумент является определяемый пользователем тип не сопоставлен идентификатор GUID.

Следующий пример приводит к возникновению ошибки C2787:

```
// C2787.cpp
#include <windows.h>
struct F {};

struct __declspec(uuid("00000000-0000-0000-c000-000000000046")) F2;

int main() {
   __uuidof(F);   // C2787
   __uuidof(F2);   // OK
}
```