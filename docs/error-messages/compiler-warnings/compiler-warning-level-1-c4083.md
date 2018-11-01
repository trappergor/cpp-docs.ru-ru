---
title: Компилятор предупреждение (уровень 1) C4083
ms.date: 11/04/2016
f1_keywords:
- C4083
helpviewer_keywords:
- C4083
ms.assetid: e7d3344e-5645-4d56-8460-d1acc9145ada
ms.openlocfilehash: 854d4a9887b8a9ada12adc94509745458a1e9523
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50516393"
---
# <a name="compiler-warning-level-1-c4083"></a>Компилятор предупреждение (уровень 1) C4083

Ожидалось «токен»; Обнаружен идентификатор «идентификатор»

Идентификатор обнаружен в недопустимом месте **#pragma** инструкции.

## <a name="example"></a>Пример

```
// C4083.cpp
// compile with: /W1 /LD
#pragma warning disable:4083    // C4083
#pragma warning(disable:4083)   //correct
```

Проверьте синтаксис [#pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) директивы.