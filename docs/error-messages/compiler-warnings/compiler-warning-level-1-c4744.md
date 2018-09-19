---
title: Предупреждение компилятора (уровень 1) C4744 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4744
dev_langs:
- C++
helpviewer_keywords:
- C4744
ms.assetid: f2a7d0b5-afd5-4926-abc3-cfbd367e3ff5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 1754977486327e06fb56a786be523c1b2fb7b917
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46068979"
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