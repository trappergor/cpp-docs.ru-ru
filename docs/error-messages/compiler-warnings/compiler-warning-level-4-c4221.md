---
title: Предупреждение компилятора (уровень 4) C4221
ms.date: 11/04/2016
f1_keywords:
- C4221
helpviewer_keywords:
- C4221
ms.assetid: 8532bd68-54dc-4526-8597-f61dcb0a0129
ms.openlocfilehash: e925f315e8506453403b0a0eda75b7c2956cc05c
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87219941"
---
# <a name="compiler-warning-level-4-c4221"></a>Предупреждение компилятора (уровень 4) C4221

использовано нестандартное расширение: "идентификатор": невозможно инициализировать с помощью адреса автоматической переменной

С помощью расширений Майкрософт по умолчанию (/Ze) можно инициализировать агрегатный тип (**массив**, **`struct`** или **`union`** ) с адресом локальной (автоматической) переменной.

## <a name="example"></a>Пример

```c
// C4221.c
// compile with: /W4
struct S
{
   int *i;
};

void func()
{
   int j;
   struct S s1 = { &j };   // C4221
}

int main()
{
}
```

Такие инициализации недопустимы в режиме совместимости ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).
