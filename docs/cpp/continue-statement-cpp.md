---
title: Оператор Continue (C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- continue_cpp
dev_langs:
- C++
helpviewer_keywords:
- continue keyword [C++]
ms.assetid: 3c94ee57-f732-4c1d-8537-d0ce5382bfd4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 88281d90ce15ced12079b3c66a74bb2f23c11034
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46099725"
---
# <a name="continue-statement-c"></a>Оператор continue (C++)

Принудительно вызывает передачу управления управляющему выражению наименьшего внешнего [сделать](../cpp/do-while-statement-cpp.md), [для](../cpp/for-statement-cpp.md), или [хотя](../cpp/while-statement-cpp.md) цикла.

## <a name="syntax"></a>Синтаксис

```
continue;
```

## <a name="remarks"></a>Примечания

Все остальные операторы текущей итерации не выполняются. Следующая итерация цикла определяется следующим образом.

- В **сделать** или **хотя** цикл, следующая итерация начинается путем повторного вычисления управляющее выражение оператора **сделать** или **хотя** инструкции.

- В **для** цикла (с использованием синтаксиса `for`(`init-expr`; `cond-expr`; `loop-expr`)), `loop-expr` предложение выполняется. Затем повторно выполняется предложение `cond-expr` и, в зависимости от результата, цикл завершается или начинается другая итерация.

В следующем примере показан как **по-прежнему** инструкция может использоваться для обхода фрагментов кода и начала выполнения следующей итерации цикла.

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

## <a name="see-also"></a>См. также

[Операторы перехода](../cpp/jump-statements-cpp.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)