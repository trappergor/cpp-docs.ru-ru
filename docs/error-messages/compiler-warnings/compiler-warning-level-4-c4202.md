---
title: Предупреждение компилятора (уровень 4) C4202
ms.date: 11/04/2016
f1_keywords:
- C4202
helpviewer_keywords:
- C4202
ms.assetid: 253293aa-97a3-4878-a2e8-c6cc9e20b1cb
ms.openlocfilehash: c66e2243ee5eca55105de27c9824ee8ced338500
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50536164"
---
# <a name="compiler-warning-level-4-c4202"></a>Предупреждение компилятора (уровень 4) C4202

использовано нестандартное расширение: «...»: параметр прототипа в списке имен

Определение функции устаревшего стиле содержит переменные аргументы. Эти определения ошибку совместимости ANSI ([/Za](../../build/reference/za-ze-disable-language-extensions.md)).

## <a name="example"></a>Пример

```
// C4202.c
// compile with: /W4
void func( a, b, ...)   // C4202
int a, b;
{}

int main()
{
}
```