---
title: Ошибка компилятора C2042
ms.date: 11/04/2016
f1_keywords:
- C2042
helpviewer_keywords:
- C2042
ms.assetid: e111788f-41ce-405a-9824-a4c1c26059e6
ms.openlocfilehash: 3302b3a529ad8af054bb29bced66bc939abcc060
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643873"
---
# <a name="compiler-error-c2042"></a>Ошибка компилятора C2042

зарезервированные слова signed и unsigned являются взаимоисключающими

Ключевые слова `signed` и `unsigned` используются в одном объявлении.

Следующий пример приводит к возникновению ошибки C2042:

```
// C2042.cpp
unsigned signed int i;   // C2042
```

Возможное решение

```
// C2042b.cpp
// compile with: /c
unsigned int i;
signed int ii;
```