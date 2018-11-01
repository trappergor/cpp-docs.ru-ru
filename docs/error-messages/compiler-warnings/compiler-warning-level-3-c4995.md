---
title: Предупреждение компилятора (уровень 3) C4995
ms.date: 11/04/2016
f1_keywords:
- C4995
helpviewer_keywords:
- C4995
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
ms.openlocfilehash: 54bc8931b5eaa3bbb5053e5c21aa2aaaa73126fb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50624800"
---
# <a name="compiler-warning-level-3-c4995"></a>Предупреждение компилятора (уровень 3) C4995

«функция»: имя помечено как #pragma deprecated

Компилятор обнаружил функцию, который был отмечен атрибутом директивы pragma [устаревшим](../../preprocessor/deprecated-c-cpp.md). Функция может не поддерживаться в будущих выпусках. Можно отключить это предупреждение с [предупреждение](../../preprocessor/warning.md) pragma (пример ниже).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4995:

```
// C4995.cpp
// compile with: /W3
#include <stdio.h>

// #pragma warning(disable : 4995)
void func1(void)
{
    printf("\nIn func1");
}

int main()
{
    func1();
    #pragma deprecated(func1)
    func1();   // C4995
}
```