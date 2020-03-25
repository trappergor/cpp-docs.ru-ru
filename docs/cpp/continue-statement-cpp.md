---
title: Оператор continue (C++)
ms.date: 11/04/2016
f1_keywords:
- continue_cpp
helpviewer_keywords:
- continue keyword [C++]
ms.assetid: 3c94ee57-f732-4c1d-8537-d0ce5382bfd4
ms.openlocfilehash: b3790ecfde0af958b3244cfdaa61524ba78d6267
ms.sourcegitcommit: 857fa6b530224fa6c18675138043aba9aa0619fb
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80180281"
---
# <a name="continue-statement-c"></a>Оператор continue (C++)

Принудительно передает управление управляющему выражению наименьшего включающего цикла [Do](../cpp/do-while-statement-cpp.md), [for](../cpp/for-statement-cpp.md)или [while](../cpp/while-statement-cpp.md) .

## <a name="syntax"></a>Синтаксис

```
continue;
```

## <a name="remarks"></a>Remarks

Все остальные операторы текущей итерации не выполняются. Следующая итерация цикла определяется следующим образом.

- В цикле **Do** или **while** Следующая итерация начинается с переоценки управляющего выражения инструкции **Do** или **while** .

- В цикле **for** (с использованием синтаксиса `for`(`init-expr`; `cond-expr`; `loop-expr`)) выполняется предложение `loop-expr`. Затем повторно выполняется предложение `cond-expr` и, в зависимости от результата, цикл завершается или начинается другая итерация.

В следующем примере показано, как можно использовать оператор **Continue** для обхода частей кода и начать следующую итерацию цикла.

## <a name="example"></a>Пример

```cpp
// continue_statement.cpp
#include <stdio.h>
int main()
{
    int i = 0;
    do
    {
        i++;
        printf_s("before the continue\n");
        continue;
        printf("after the continue, should never print\n");
     } while (i < 3);

     printf_s("after the do loop\n");
}
```

```Output
before the continue
before the continue
before the continue
after the do loop
```

## <a name="see-also"></a>См. также раздел

[Операторы перехода](../cpp/jump-statements-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
