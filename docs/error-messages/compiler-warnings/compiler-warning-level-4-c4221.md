---
title: Предупреждение компилятора (уровень 4) C4221
ms.date: 11/04/2016
f1_keywords:
- C4221
helpviewer_keywords:
- C4221
ms.assetid: 8532bd68-54dc-4526-8597-f61dcb0a0129
ms.openlocfilehash: fa87c240472df2926753781f0f14cbd69752de00
ms.sourcegitcommit: 3ee06ec53153cf21910fc8cfef78a4f25f9633f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/26/2019
ms.locfileid: "74541929"
---
# <a name="compiler-warning-level-4-c4221"></a>Предупреждение компилятора (уровень 4) C4221

использовано нестандартное расширение: "идентификатор": невозможно инициализировать с помощью адреса автоматической переменной

Используя расширения Майкрософт по умолчанию (/Ze), можно инициализировать агрегатный тип (**массив**, `struct`или **объединение**) с адресом локальной (автоматической) переменной.

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