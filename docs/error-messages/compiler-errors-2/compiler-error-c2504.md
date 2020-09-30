---
title: Ошибка компилятора C2504
ms.date: 11/04/2016
f1_keywords:
- C2504
helpviewer_keywords:
- C2504
ms.assetid: c9e002a6-a4ee-4ba7-970e-edf4adb83692
ms.openlocfilehash: 0860f4b860b370f96c2c29046b090d5b205c63ba
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91509392"
---
# <a name="compiler-error-c2504"></a>Ошибка компилятора C2504

"класс": базовый класс не определен

Базовый класс объявлен, но не определен.  Возможные причины:

1. Отсутствует включаемый файл.

1. Внешний базовый класс не объявлен с [модификатором extern](../../cpp/extern-cpp.md).

Следующий пример приводит к возникновению ошибки C2504:

```cpp
// C2504.cpp
// compile with: /c
class A;
class B : public A {};   // C2504
```

Хорошо

```
class C{};
class D : public C {};
```
