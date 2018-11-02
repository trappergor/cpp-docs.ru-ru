---
title: Предупреждение компилятора (уровень 4) C4204
ms.date: 11/04/2016
f1_keywords:
- C4204
helpviewer_keywords:
- C4204
ms.assetid: 298d2880-6737-448e-b711-15572d540200
ms.openlocfilehash: e16cb9fb59ee6ec24bb9b68dad1be9432d9eee3f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50573008"
---
# <a name="compiler-warning-level-4-c4204"></a>Предупреждение компилятора (уровень 4) C4204

использовано нестандартное расширение: неконстантный составной инициализатор

В расширениях Майкрософт (/Ze) вы можете инициализировать агрегатные типы (массивы, структуры, объединения и классы) со значениями, которые не являются константами.

## <a name="example"></a>Пример

```
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

Подобная инициализация не допускается в режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).