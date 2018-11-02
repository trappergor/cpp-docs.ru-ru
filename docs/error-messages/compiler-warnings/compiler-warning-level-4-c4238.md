---
title: Предупреждение компилятора (уровень 4) C4238
ms.date: 11/04/2016
f1_keywords:
- C4238
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
ms.openlocfilehash: c5ffa07b06f010d10edc14aa7576bb614aa9dd04
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50471907"
---
# <a name="compiler-warning-level-4-c4238"></a>Предупреждение компилятора (уровень 4) C4238

использовано нестандартное расширение: правостороннего значения класса в качестве левостороннего значения

Для совместимости с предыдущими версиями Visual c++, расширения Microsoft (**/Ze**) можно будет использовать тип класса, как rvalue в контексте, который явно или неявно принимает его адрес. В некоторых случаях, как показано в примере ниже это может быть опасно.

## <a name="example"></a>Пример

```
// C4238.cpp
// compile with: /W4 /c
struct C {
   C() {}
};

C * pC = &C();   // C4238
```

Такое использование вызывает ошибку совместимости ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).