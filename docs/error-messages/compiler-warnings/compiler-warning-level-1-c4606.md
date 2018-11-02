---
title: Предупреждение компилятора (уровень 1) C4606
ms.date: 11/04/2016
f1_keywords:
- C4606
helpviewer_keywords:
- C4606
ms.assetid: c1b45fb6-672b-42eb-9e1c-c67b3e4150d3
ms.openlocfilehash: e471ca3e478d1166b150e49bf25efa4b9d5803cb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50569277"
---
# <a name="compiler-warning-level-1-c4606"></a>Предупреждение компилятора (уровень 1) C4606

\#в директиве pragma warning: «warning_number» игнорируется; Предупреждения анализа кода не связаны с уровнями предупреждений

Для предупреждения модуля анализа кода, только `error`, `once`, и `default` поддерживаются с [предупреждение](../../preprocessor/warning.md) директивы pragma.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4606.

```
// C4606.cpp
// compile with: /c /W1
#pragma warning(1: 6001)   // C4606
#pragma warning(once: 6001)   // OK
```