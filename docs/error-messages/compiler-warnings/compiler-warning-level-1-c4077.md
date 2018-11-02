---
title: Предупреждение компилятора (уровень 1) C4077
ms.date: 11/04/2016
f1_keywords:
- C4077
helpviewer_keywords:
- C4077
ms.assetid: c2d28805-b33f-41ad-afba-33b3f788c649
ms.openlocfilehash: 5171ee79c3afd32e847483568fbbf90222747509
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50442216"
---
# <a name="compiler-warning-level-1-c4077"></a>Предупреждение компилятора (уровень 1) C4077

неизвестный параметр check_stack

Старая форма прагмы **check_stack** используется с неизвестным аргументом. Аргумент должен быть `+`, `-`, `(on)`, `(off)`или быть пустым.

Компилятор игнорирует эту прагму и оставляет проверку стека неизмененной.

## <a name="example"></a>Пример

```
// C4077.cpp
// compile with: /W1 /LD
#pragma check_stack yes // C4077
#pragma check_stack +    // Correct old form
#pragma check_stack (on) // Correct new form
```