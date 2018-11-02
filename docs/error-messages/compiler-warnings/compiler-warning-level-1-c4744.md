---
title: Предупреждение компилятора (уровень 1) C4744
ms.date: 11/04/2016
f1_keywords:
- C4744
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
ms.openlocfilehash: 2118a32af8b99d35c1e1a6691561391ec5d2b8cc
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50606015"
---
# <a name="compiler-warning-level-1-c4744"></a>Предупреждение компилятора (уровень 1) C4744

«var» имеет различные типы в «файл1» и «файл2»: «тип1» и «тип2»

Внешняя переменная или ссылаться на определенные в двух файлах имеет различные типы в этих файлах.  Чтобы решить, сделать определения типов одинаковыми или изменить имя переменной в один из файлов.

C4744 создается, только в том случае, когда файлы компилируются с помощью параметра/GL.  Дополнительные сведения см. в разделе [/GL (оптимизация всей программы)](../../build/reference/gl-whole-program-optimization.md).

> [!NOTE]
>  C4744 обычно возникает в файлах C (C++), так как в C++ имя переменной снабжен сведения о типе.  Когда образец (см. ниже) представляет компиляции как C++, вы получите сообщение об ошибке компоновщика LNK2019.

## <a name="example"></a>Пример

Этот пример содержит первое определение.

```
// C4744.c
// compile with: /c /GL
int global;
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4744.

```
// C4744b.c
// compile with: C4744.c /GL /W1
// C4744 expected
#include <stdio.h>

extern unsigned global;

main()
{
    printf_s("%d\n", global);
}
```