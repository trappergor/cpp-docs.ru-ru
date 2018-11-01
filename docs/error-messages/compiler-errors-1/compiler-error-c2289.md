---
title: Ошибка компилятора C2289
ms.date: 11/04/2016
f1_keywords:
- C2289
helpviewer_keywords:
- C2289
ms.assetid: cb41a29e-1b06-47dc-bfce-8d73bd63a0df
ms.openlocfilehash: 9fe9b765af72a8864e3e899cafcf648a9facb67e
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50528132"
---
# <a name="compiler-error-c2289"></a>Ошибка компилятора C2289

Множественное использование одного и того же квалификатора типа

В объявлении типа или определении квалификатор типа (`const`, `volatile`, `signed`или `unsigned`) используется более одного раза, что вызывает ошибку совместимости ANSI(**/Za**).

При компиляции следующего примера возникнет ошибка C2286:

```
// C2289.cpp
// compile with: /Za /c
volatile volatile int i;   // C2289
volatile int j;   // OK
```