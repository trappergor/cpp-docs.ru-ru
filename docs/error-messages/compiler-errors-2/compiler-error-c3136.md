---
title: Ошибка компилятора C3136
ms.date: 10/03/2018
f1_keywords:
- C3136
helpviewer_keywords:
- C3136
ms.assetid: c77103cd-00f7-408e-b74b-4f8562039d31
ms.openlocfilehash: e32ffca067c3b25120301527e7a708d53001d541
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62376254"
---
# <a name="compiler-error-c3136"></a>Ошибка компилятора C3136

«интерфейс»: COM-интерфейс может наследовать только от другого интерфейса COM, «интерфейс» не является COM-интерфейс

Интерфейс, к которому применен [атрибут интерфейса](../../windows/attributes/interface-attributes.md) наследует от интерфейса, который не является COM-интерфейса. COM-интерфейс наследует от `IUnknown`. Любому интерфейсу предшествует атрибут интерфейса — это COM-интерфейс.

Следующий пример приводит к возникновению ошибки C3136:

```
// C3136.cpp
#include "unknwn.h"

__interface A   // C3136
// try the following line instead
// _interface A : IUnknown
{
   int a();
};

[object]
__interface B : A
{
   int aa();
};
```