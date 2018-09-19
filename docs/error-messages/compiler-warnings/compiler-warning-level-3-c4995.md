---
title: Предупреждение компилятора (уровень 3) C4995 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4995
dev_langs:
- C++
helpviewer_keywords:
- C4995
ms.assetid: c6b61755-4730-4947-ad4d-d1c2bc82585a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: c5ae389fef72681c6a8b31c9790c6773535f467d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46053483"
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