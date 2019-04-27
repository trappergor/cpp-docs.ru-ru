---
title: Ошибка компилятора C2598
ms.date: 11/04/2016
f1_keywords:
- C2598
helpviewer_keywords:
- C2598
ms.assetid: 40777c62-39ba-441e-b081-f49f94b43547
ms.openlocfilehash: 521a67bdf1e1f64853a3f87933b3fa714c8e33f0
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62257755"
---
# <a name="compiler-error-c2598"></a>Ошибка компилятора C2598

компоновки должен определяться в глобальной области видимости

Описатель компоновки объявляется в локальной области видимости.

Следующий пример приводит к возникновению ошибки C2598:

```
// C2598.cpp
// compile with: /c
void func() {
   extern "C" int func2();   // C2598
}

extern "C" int func( int i );
```