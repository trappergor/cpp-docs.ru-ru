---
title: Ошибка компилятора C2719
ms.date: 11/04/2016
f1_keywords:
- C2719
helpviewer_keywords:
- C2719
ms.assetid: ea6236d3-8286-45cc-9478-c84ad3dd3c8e
ms.openlocfilehash: d635601fbf8b36218fb47c09444f3f5d023c823e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62383091"
---
# <a name="compiler-error-c2719"></a>Ошибка компилятора C2719

parameter: формальный параметр с __declspec(align('#')) не будет выровнен

[Выровнять](../../cpp/align-cpp.md) `__declspec` модификатора не допускается в параметрах функций. Выравнивание параметров функции контролируется используемым соглашением о вызовах. Дополнительные сведения см. в разделе [соглашения о вызовах](../../cpp/calling-conventions.md).

В следующем примере показано возникновение ошибки C2719 и приводятся сведения по ее устранению.

```
// C2719.cpp
void func(int __declspec(align(32)) i);   // C2719
// try the following line instead
// void func(int i);
```