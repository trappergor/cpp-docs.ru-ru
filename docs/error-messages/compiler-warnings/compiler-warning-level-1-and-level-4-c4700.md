---
title: "Предупреждение компилятора (уровень 1 и уровень 4) C4700 | Документы Microsoft"
ms.custom: 
ms.date: 02/21/2018
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4700
dev_langs:
- C++
helpviewer_keywords:
- C4700
ms.assetid: 2da0deb4-77dd-4b05-98d3-b78d74ac4ca7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 00b871d6199338cc3040d6bddedb85f8732dfccd
ms.sourcegitcommit: 4e416049665819ac62f5300ddf86e94adede4ba0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/23/2018
---
# <a name="compiler-warning-level-1-and-level-4-c4700"></a>Предупреждение компилятора (уровень 1 и уровень 4) C4700

> неинициализированная локальная переменная "*имя*" используется

Локальная переменная *имя* было *используется*, то есть, считывается, до того, как оно было присвоено значение. В C и C++ локальные переменные не инициализированы по умолчанию. Неинициализированные переменные может содержать любое значение, и их использование приводит к неопределенному поведению. Предупреждение C4700 почти всегда указывает ошибку, которая может привести к непредсказуемым результатам или сбои в программе.

Чтобы устранить эту проблему, инициализации локальных переменных при их объявлении или присвоить значение их перед их использованием. Функция может использоваться для инициализации переменная, передаваемая как параметр по ссылке или при его адрес передается как параметр-указатель.

## <a name="example"></a>Пример

Этот пример приводит к возникновению ошибки C4700, при использовании переменных t, u и v прежде чем они инициализируются и показывает, какие значения сборки мусора, что может привести к. Переменные x, y и z не вызвать предупреждение, так как они инициализируются перед использованием:

```cpp
// c4700.cpp
// compile by using: cl /EHsc /W4 c4700.cpp
#include <iostream>

// function takes an int reference to initialize
void initialize(int& i)
{
    i = 21;
}

int main()
{
    int s, t, u, v;   // Danger, uninitialized variables

    s = t + u + v;    // C4700: t, u, v used before initialization
    std::cout << "Value in s: " << s << std::endl;

    int w, x;         // Danger, uninitialized variables
    initialize(x);    // fix: call function to init x before use
    int y{10};        // fix: initialize y, z when declared
    int z{11};        // This C++11 syntax is recommended over int z = 11;

    w = x + y + z;    // Okay, all values initialized before use
    std::cout << "Value in w: " << w << std::endl;
}
```

При этом код выполнения, t, u и v не инициализированы и выходные данные для s непредсказуем:

```Output
Value in s: 37816963
Value in w: 42
```
