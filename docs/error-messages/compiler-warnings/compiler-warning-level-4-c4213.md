---
title: Предупреждение компилятора (уровень 4) C4213
ms.date: 11/04/2016
f1_keywords:
- C4213
helpviewer_keywords:
- C4213
ms.assetid: 59fc3f61-ebd2-499e-99d7-f57bec11eda1
ms.openlocfilehash: e462fcc2d0283d2519796127612123f7d792d00e
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80161299"
---
# <a name="compiler-warning-level-4-c4213"></a>Предупреждение компилятора (уровень 4) C4213

использовано нестандартное расширение: приведение к l-значению

Используя расширения Майкрософт по умолчанию (/Ze), можно использовать приведения в левой части оператора присваивания.

## <a name="example"></a>Пример

```c
// C4213.c
// compile with: /W4
void *a;
void f()
{
   int   i[3];
   a = &i;
   *(( int * )a )++ = 3;  // C4213
}

int main()
{
}
```

Такие приведения недопустимы в режиме совместимости ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).
