---
title: Ошибка компилятора C2479
ms.date: 11/04/2016
f1_keywords:
- C2479
helpviewer_keywords:
- C2479
ms.assetid: c74c7869-e65b-4ca1-b6fa-eb39fed4458a
ms.openlocfilehash: 8b3b226ccbe42ec88ed92c64b97256d80a983254
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50611436"
---
# <a name="compiler-error-c2479"></a>Ошибка компилятора C2479

«Идентификатор»: «allocate ()» допускается только для статических элементов данных

`__declspec( allocate())` Синтаксис может использоваться только для статических данных.

Следующий пример приводит к возникновению ошибки C2479:

```
// C2479.cpp
// compile with: /c
#pragma section("mycode", read)
static __declspec(allocate("mycode")) void DoNothing() {}   // C2479
__declspec(allocate("mycode"))  int i = 0;   // OK
```