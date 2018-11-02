---
title: Ошибка компилятора C2504
ms.date: 11/04/2016
f1_keywords:
- C2504
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
ms.openlocfilehash: 8f428699aa14cbd1f021a57ed8dcabefa8b24c16
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50444395"
---
# <a name="compiler-error-c2504"></a>Ошибка компилятора C2504

«класс»: базовый класс не определен

Базовый класс объявлен, но никогда не определен.  Возможные причины:

1. Пропущен включаемый файл.

1. Внешний базовый класс не объявлен с [extern](../../cpp/using-extern-to-specify-linkage.md).

Следующий пример приводит к возникновению ошибки C2504:

```
// C2504.cpp
// compile with: /c
class A;
class B : public A {};   // C2504
```

ХОРОШО

```
class C{};
class D : public C {};
```