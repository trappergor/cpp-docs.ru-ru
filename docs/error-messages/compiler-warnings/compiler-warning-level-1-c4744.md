---
title: Предупреждение компилятора (уровень 1) C4744
ms.date: 11/04/2016
f1_keywords:
- C4744
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
ms.openlocfilehash: f932b1bcdf011678d4f85e0edf1e116a954b59fe
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81367382"
---
# <a name="compiler-warning-level-1-c4744"></a>Предупреждение компилятора (уровень 1) C4744

'var' имеет другой тип в 'file1' и 'file2': 'type1' и 'type2'

Внешняя переменная, на которая ссылаются или определяются в двух файлах, имеет разные типы в этих файлах.  Чтобы решить, либо сделать определения типа одинаковыми, либо изменить имя переменной в одном из файлов.

C4744 излучается только при компилировании файлов с помощью /GL.  Дополнительные сведения см. в разделе [/GL (оптимизация всей программы)](../../build/reference/gl-whole-program-optimization.md).

> [!NOTE]
> C4744 обычно происходит в файлах C (не C, так и в C,, потому что в C', переменное имя украшено информацией типа.  Когда образец (см. ниже) компилируется как C, вы получите ошибку linker LNK2019.

## <a name="example"></a>Пример

Этот пример содержит первое определение.

```c
// C4744.c
// compile with: /c /GL
int global;
```

## <a name="example"></a>Пример

Следующий образец генерирует C4744.

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
