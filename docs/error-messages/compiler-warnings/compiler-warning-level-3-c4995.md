---
title: Предупреждение компилятора (уровень 3) C4995
ms.date: 11/04/2016
f1_keywords:
- C4995
helpviewer_keywords:
- C4995
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
ms.openlocfilehash: c361563c2272da002a0edc185cc924c64f6b5e5c
ms.sourcegitcommit: 573b36b52b0de7be5cae309d45b68ac7ecf9a6d8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/10/2019
ms.locfileid: "74991661"
---
# <a name="compiler-warning-level-3-c4995"></a>Предупреждение компилятора (уровень 3) C4995

"функция": имя помечено как #pragma устарело

Компилятор обнаружил функцию, которая была отмечена как [нерекомендуемая](../../preprocessor/deprecated-c-cpp.md)директива pragma. Функция может не поддерживаться в будущих выпусках. Это предупреждение можно отключить с помощью прагма-директивы [warning](../../preprocessor/warning.md) (пример ниже).

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4995:

```cpp
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
