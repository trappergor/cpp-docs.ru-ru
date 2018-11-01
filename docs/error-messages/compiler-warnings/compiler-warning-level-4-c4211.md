---
title: Предупреждение компилятора (уровень 4) C4211
ms.date: 11/04/2016
f1_keywords:
- C4211
helpviewer_keywords:
- C4211
ms.assetid: 3eea3455-6faa-4cdb-8730-73db7026bd1f
ms.openlocfilehash: f1e85591d8ec989d806eb43a6be99bdb1dc62fb4
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50659333"
---
# <a name="compiler-warning-level-4-c4211"></a>Предупреждение компилятора (уровень 4) C4211

использовано нестандартное расширение: переопределение extern в static

В расширениях Майкрософт по умолчанию (/Ze), можно переопределить `extern` идентификатор, что **статических**.

## <a name="example"></a>Пример

```
// C4211.c
// compile with: /W4
extern int i;
static int i;   // C4211

int main()
{
}
```

Такие переопределения недействительны в режиме совместимости с ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).

## <a name="see-also"></a>См. также

