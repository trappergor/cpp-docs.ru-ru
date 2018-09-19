---
title: Предупреждение компилятора (уровень 4) C4764 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4764
dev_langs:
- C++
helpviewer_keywords:
- C4764
ms.assetid: 7bd4296f-966b-484c-bf73-8dbc8e85b4a9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9c3b80e09736e03852a13073b1ba4ea3c506c5e2
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46081899"
---
# <a name="compiler-warning-level-4-c4764"></a>Предупреждение компилятора (уровень 4) C4764

Для перехваченных объектов выравнивание не может превышать 16 байт

Задано выравнивание, превышающее 16 байтов. На некоторых платформах при возникновении исключения функции принудительно устанавливается выравнивание стека, не превышающее 16 байтов.

## <a name="example"></a>Пример

При компиляции следующего примера выдается предупреждение C4764:

```
// C4764.cpp
// compile with: /W4 /EHsc
// processor: x64 IPF
#include <stdio.h>

class A
{
public:
    int x;
};

typedef __declspec(align(32)) A ALIGNEDA;

int main()
{
    ALIGNEDA a;
    try
    {
        a.x = 15;
        throw a;
    }
    catch (ALIGNEDA b) // can’t align b to > 16 bytes
    {
        printf_s("%d\n", b.x);
    }
}   // C4764
```