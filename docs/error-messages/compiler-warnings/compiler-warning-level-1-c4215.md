---
title: Предупреждение компилятора (уровень 4) C4215
ms.date: 11/04/2016
f1_keywords:
- C4215
helpviewer_keywords:
- C4215
ms.assetid: f2aab64d-1bab-4f75-95ee-89e1263047b1
ms.openlocfilehash: b62f382759c7e4c9dc888cf75d4df07a063df571
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80199866"
---
# <a name="compiler-warning-level-1-c4215"></a>Предупреждение компилятора (уровень 4) C4215

использовано нестандартное расширение: long float

Расширения Майкрософт по умолчанию (/Ze) обрабатывают **Long float** как **Double**. ANSI Compatibility ([/Za](../../build/reference/za-ze-disable-language-extensions.md)) не поддерживает. Используйте **Double** для обеспечения совместимости.

Следующий пример приводит к возникновению ошибки C4215:

```cpp
// C4215.cpp
// compile with: /W1 /LD
long float a;   // C4215

// use the line below to resolve the warning
// double a;
```
