---
title: Предупреждение компилятора (уровень 4) C4234
ms.date: 11/04/2016
f1_keywords:
- C4234
helpviewer_keywords:
- C4234
ms.assetid: f7fecd5c-8248-4fde-8446-502aedc357ca
ms.openlocfilehash: 314ee068fb2be6148304360b0aaa3bd8029c283b
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50441019"
---
# <a name="compiler-warning-level-4-c4234"></a>Предупреждение компилятора (уровень 4) C4234

использовано нестандартное расширение: «ключевое слово» зарезервировано для будущего использования

Компилятор не еще реализует ключевое слово, которое вы использовали.

Это предупреждение автоматически повышается до ошибки. Если вы хотите изменить это поведение, используйте [#pragma warning](../../preprocessor/warning.md). Например, чтобы сделать C4234 в предупреждение уровня 4,

```
#pragma warning(2:4234)
```

в файле исходного кода.