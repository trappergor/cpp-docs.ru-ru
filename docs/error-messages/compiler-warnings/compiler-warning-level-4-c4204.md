---
title: Предупреждение компилятора (уровень 4) C4204
ms.date: 11/04/2016
f1_keywords:
- C4204
helpviewer_keywords:
- C4204
ms.assetid: 298d2880-6737-448e-b711-15572d540200
ms.openlocfilehash: ecbe8bddd3f868070470555e79608ac1ecce380a
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541674"
---
# <a name="compiler-warning-level-4-c4204"></a>Предупреждение компилятора (уровень 4) C4204

использовано нестандартное расширение: неконстантный агрегатный инициализатор

С помощью расширений Майкрософт (/Ze) можно инициализировать статистические типы (массивы, структуры, объединения и классы) со значениями, которые не являются константами.

## <a name="example"></a>Пример

```c
// C4204.c
// compile with: /W4
int func1()
{
   return 0;
}
struct S1
{
   int i;
};

int main()
{
   struct S1 s1 = { func1() };   // C4204
   return s1.i;
}
```

Такие инициализации недопустимы в режиме совместимости ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).