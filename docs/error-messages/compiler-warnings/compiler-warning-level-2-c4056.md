---
title: Предупреждение компилятора (уровень 2) C4056
ms.date: 11/04/2016
f1_keywords:
- C4056
helpviewer_keywords:
- C4056
ms.assetid: a3c3a9b8-ec30-452d-96cb-3694adcce789
ms.openlocfilehash: 6046c41bfe9d787732a2cbd50ce3b0d0d9fdb26f
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80174353"
---
# <a name="compiler-warning-level-2-c4056"></a>Предупреждение компилятора (уровень 2) C4056

переполнение в константных арифметических операциях с плавающей точкой

Арифметическая константа с плавающей запятой формирует результат, превышающий максимально допустимое значение.

Это предупреждение может быть вызвано оптимизацией компилятора, выполненной во время постоянной арифметики. Вы можете спокойно проигнорировать это предупреждение, если оно исчезает при отключении оптимизации ([/OD](../../build/reference/od-disable-debug.md)).

Следующий пример приводит к возникновению ошибки C4056:

```cpp
// C4056.cpp
// compile with: /W2 /LD
#pragma warning (default : 4056)
float fp_val = 1.0e300 * 1.0e300;   // C4056
```
