---
title: Предупреждение компилятора (уровень 4) C4235
ms.date: 11/04/2016
f1_keywords:
- C4235
helpviewer_keywords:
- C4235
ms.assetid: d4214799-d62c-4674-b4e2-9e201c303303
ms.openlocfilehash: 80ad388b26b2b972aa1301c1f335d0361a75f15f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50559850"
---
# <a name="compiler-warning-level-4-c4235"></a>Предупреждение компилятора (уровень 4) C4235

использовано нестандартное расширение: «ключевое слово» не поддерживается в этой архитектуре

Компилятор не поддерживает ключевое слово, которое вы использовали.

Это предупреждение автоматически повышается до ошибки. Если вы хотите изменить это поведение, используйте [#pragma warning](../../preprocessor/warning.md). Например чтобы сделать C4235 предупреждение уровня 2, используйте следующую строку кода

```
#pragma warning(2:4235)
```

в файле исходного кода.