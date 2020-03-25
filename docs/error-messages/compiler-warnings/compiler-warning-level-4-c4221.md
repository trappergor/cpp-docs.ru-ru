---
title: Предупреждение компилятора (уровень 4) C4221
ms.date: 11/04/2016
f1_keywords:
- C4221
helpviewer_keywords:
- C4221
ms.assetid: 8532bd68-54dc-4526-8597-f61dcb0a0129
ms.openlocfilehash: fa948865685af4cbd6a865cfbf1d8546b29ab280
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161143"
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
