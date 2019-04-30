---
title: Предупреждение компилятора (уровень 4) C4238
ms.date: 11/04/2016
f1_keywords:
- C4238
helpviewer_keywords:
- C4238
ms.assetid: 5d4051d3-7b0f-43ea-8c8d-d194bfdceb71
ms.openlocfilehash: c5ffa07b06f010d10edc14aa7576bb614aa9dd04
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62401037"
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