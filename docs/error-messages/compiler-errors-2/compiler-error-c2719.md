---
title: Ошибка компилятора C2719
ms.date: 11/04/2016
f1_keywords:
- C2719
helpviewer_keywords:
- C2719
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
ms.openlocfilehash: 574a04923c20c3104083a6aa05a71838e7ec13d2
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74760508"
---
# <a name="compiler-error-c2719"></a>Ошибка компилятора C2719

parameter: формальный параметр с __declspec(align('#')) не будет выровнен

Модификатор " [выровняйте](../../cpp/align-cpp.md) `__declspec`" не разрешен для параметров функции. Выравнивание параметров функции контролируется используемым соглашением о вызовах. Дополнительные сведения см. в разделе [соглашения о вызовах](../../cpp/calling-conventions.md).

В следующем примере показано возникновение ошибки C2719 и приводятся сведения по ее устранению.

```cpp
// C2719.cpp
void func(int __declspec(align(32)) i);   // C2719
// try the following line instead
// void func(int i);
```
