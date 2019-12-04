---
title: Ошибка компилятора C2289
ms.date: 11/04/2016
f1_keywords:
- C2289
helpviewer_keywords:
- C2289
ms.assetid: cb41a29e-1b06-47dc-bfce-8d73bd63a0df
ms.openlocfilehash: 32afd6b99b84fba1ef9c2c701306abc67488337c
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74759130"
---
# <a name="compiler-error-c2289"></a>Ошибка компилятора C2289

Множественное использование одного и того же квалификатора типа

В объявлении типа или определении квалификатор типа (`const`, `volatile`, `signed`или `unsigned`) используется более одного раза, что вызывает ошибку совместимости ANSI( **/Za**).

При компиляции следующего примера возникнет ошибка C2286:

```cpp
// C2289.cpp
// compile with: /Za /c
volatile volatile int i;   // C2289
volatile int j;   // OK
```
