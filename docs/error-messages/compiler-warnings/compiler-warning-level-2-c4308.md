---
title: Предупреждение компилятора (уровень 2) C4308
ms.date: 11/04/2016
f1_keywords:
- C4308
helpviewer_keywords:
- C4308
ms.assetid: d4e5c53c-71b2-4bbc-8a7c-3a2a3180d9d9
ms.openlocfilehash: f97d66f9e3445d022adc3362532774b15ea09961
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50443541"
---
# <a name="compiler-warning-level-2-c4308"></a>Предупреждение компилятора (уровень 2) C4308

Отрицательная целая константа преобразована к беззнаковому типу

Выражение константы отрицательное целое число преобразуется в тип без знака. Результат выражения имеет вероятно смысла.

## <a name="example"></a>Пример

```
// C4308.cpp
// compile with: /W2
unsigned int u = (-5 + 3U);   // C4308

int main()
{
}
```