---
title: Предупреждение компилятора (уровень 4) C4215
ms.date: 11/04/2016
f1_keywords:
- C4215
helpviewer_keywords:
- C4215
ms.assetid: f2aab64d-1bab-4f75-95ee-89e1263047b1
ms.openlocfilehash: aeab5a90647015a8848d7c2af62f7d7fc6932900
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87223282"
---
# <a name="compiler-warning-level-1-c4215"></a>Предупреждение компилятора (уровень 4) C4215

использовано нестандартное расширение: long float

Расширения Майкрософт по умолчанию (/Ze) обрабатывают значение **Long float** как **`double`** . ANSI Compatibility ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) не поддерживает. Используйте **`double`** для обеспечения совместимости.

Следующий пример приводит к возникновению ошибки C4215:

```cpp
// C4215.cpp
// compile with: /W1 /LD
long float a;   // C4215

// use the line below to resolve the warning
// double a;
```
