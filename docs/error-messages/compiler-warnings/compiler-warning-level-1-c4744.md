---
title: Предупреждение компилятора (уровень 1) C4744
ms.date: 11/04/2016
f1_keywords:
- C4744
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
ms.openlocfilehash: f6954ae7966edf200249bb5d10f0dfb011bcef22
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74051548"
---
# <a name="compiler-warning-level-1-c4744"></a>Предупреждение компилятора (уровень 1) C4744

"var" имеет другой тип в "file1" и "File2": "тип1" и "тип2"

Внешняя переменная, упоминаемая или определенная в двух файлах, имеет разные типы в этих файлах.  Чтобы устранить эту проблему, либо сделайте определения типов одинаковыми, либо измените имя переменной в одном из файлов.

C4744 создается только при компиляции файлов с помощью параметра/GL.  Дополнительные сведения см. в разделе [/GL (оптимизация всей программы)](../../build/reference/gl-whole-program-optimization.md).

> [!NOTE]
>  C4744 обычно встречаются в файлах C C++(не), так C++ как в имени переменной заданы сведения о типе.  Когда пример (ниже) компилируется как C++, вы получите ошибку компоновщика LNK2019.

## <a name="example"></a>Пример

Этот образец содержит первое определение.

```c
// C4744.c
// compile with: /c /GL
int global;
```

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4744.

```c
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