---
title: Неустранимая ошибка C1018
ms.date: 11/04/2016
f1_keywords:
- C1018
helpviewer_keywords:
- C1018
ms.assetid: 2ceb8a99-30b2-4b80-bf42-e9f3305b3c52
ms.openlocfilehash: 327bc0d5200fc348611da107257f2086063648fa
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50532674"
---
# <a name="fatal-error-c1018"></a>Неустранимая ошибка C1018

Непредвиденный #elif

Директива `#elif` встречается за пределами конструкции `#if`, `#ifdef`или `#ifndef` . Используйте `#elif` только в одной из этих конструкций.

При компиляции следующего примера возникнет ошибка C1018:

```
// C1018.cpp
#elif      // C1018
#endif

int main() {}
```

Возможное решение:

```
// C1018b.cpp
#if 1
#elif
#endif

int main() {}
```