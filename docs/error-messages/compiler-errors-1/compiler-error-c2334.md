---
title: Ошибка компилятора C2334
ms.date: 11/04/2016
f1_keywords:
- C2334
helpviewer_keywords:
- C2334
ms.assetid: 36142855-e00b-4bbf-80f5-a301edeff46e
ms.openlocfilehash: 4f068792193fd22ccddc39f9afc555e7c8672d8c
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50512981"
---
# <a name="compiler-error-c2334"></a>Ошибка компилятора C2334

непредвиденные лексемы выше ": или {"; пропуск вероятного тела функции

Следующий пример приводит к возникновению ошибки C2334. Эта ошибка возникает после ошибка C2059:

```
// C2334.cpp
// compile with: /c
// C2059 expected
struct s1 {
   s1   {}   // C2334
   s1() {}   // OK
};
```