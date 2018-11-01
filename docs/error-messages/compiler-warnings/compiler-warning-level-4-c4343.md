---
title: Предупреждение компилятора (уровень 4) C4343
ms.date: 11/04/2016
f1_keywords:
- C4343
helpviewer_keywords:
- C4343
ms.assetid: a721b710-e04f-4d15-b678-e4a2c8fd0181
ms.openlocfilehash: c8f0bb514a3da932500f986e50a20af0947827c5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50475807"
---
# <a name="compiler-warning-level-4-c4343"></a>Предупреждение компилятора (уровень 4) C4343

\#Директива #pragma optimize("g",OFF) отменяет параметр /Og

Это предупреждение, используемое только для компилятора Itanium Processor Family (IPF), служит для оповещения о том, что параметр компилятора [/Og](../../preprocessor/optimize.md) был переопределен директивой pragma [optimize](../../build/reference/og-global-optimizations.md) .

Следующий пример приводит к возникновению предупреждения C4343:

```
// C4343.cpp
// compile with: /Og /W4 /LD
// processor: IPF
#pragma optimize ("g", off)   // C4343
```