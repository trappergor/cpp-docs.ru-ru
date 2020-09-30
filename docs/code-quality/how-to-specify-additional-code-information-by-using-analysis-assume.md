---
title: Использование _Analysis_assume для указания анализа кода
ms.date: 11/04/2016
ms.topic: conceptual
f1_keywords:
- _Analysis_assume
helpviewer_keywords:
- _Analysis_assume
ms.assetid: 51205d97-4084-4cf4-a5ed-3eeaf67deb1b
ms.openlocfilehash: f427afdcab07b41430a5d4b5fc7f300aa671e30b
ms.sourcegitcommit: a1676bf6caae05ecd698f26ed80c08828722b237
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/29/2020
ms.locfileid: "91503291"
---
# <a name="how-to-specify-additional-code-information-by-using-_analysis_assume"></a>Инструкции. Указание дополнительных сведений о коде с помощью _Analysis_assume

Вы можете предоставить подсказки средству анализа кода для кода C/C++, который поможет анализировать процесс анализа и сократить число предупреждений. Чтобы предоставить дополнительные сведения, используйте следующую функцию:

`_Analysis_assume(`  `expr`  `)`

`expr` — любое выражение, для которого предполагается вычисление значения true.

Средство анализа кода предполагает, что условие, представленное выражением, имеет значение true в точке, где отображается функция, и остается истинной до тех пор, пока выражение не будет изменено, например, путем присваивания переменной.

> [!NOTE]
> `_Analysis_assume` не влияет на оптимизацию кода. Вне средства анализа кода `_Analysis_assume` определяется как отсутствие операций.

## <a name="example"></a>Пример

Следующий код используется `_Analysis_assume` для исправления предупреждения анализа кода [C6388](../code-quality/c6388.md):

```cpp
#include<windows.h>
#include<codeanalysis\sourceannotations.h>

using namespace vc_attributes;

//requires pc to be null
void f([Pre(Null=Yes)] char* pc);

// calls free and sets ch to null
void FreeAndNull(char** ch);

void test()
{
    char pc = (char)malloc(5);
    FreeAndNull(&pc);
    _Analysis_assume(pc == NULL);
    f(pc);
}
```

## <a name="see-also"></a>См. также раздел

- [__assume](../intrinsics/assume.md)
