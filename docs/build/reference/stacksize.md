---
title: STACKSIZE
ms.date: 11/04/2016
f1_keywords:
- STACKSIZE
helpviewer_keywords:
- STACKSIZE .def file statement
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
ms.openlocfilehash: de2aa99375f588d682b714632590ba8e0db8ddcb
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50597227"
---
# <a name="stacksize"></a>STACKSIZE

Задает размер стека (в байтах).

```
STACKSIZE reserve[,commit]
```

## <a name="remarks"></a>Примечания

Эквивалентный способ стека — с помощью [выделение памяти в стеке](../../build/reference/stack-stack-allocations.md) (/ STACK) параметр. См. в документации, на этот вариант, Дополнительные сведения *зарезервировать* и `commit` аргументы.

Этот параметр не влияет на библиотеки DLL.

## <a name="see-also"></a>См. также

[Правила для операторов определения модуля](../../build/reference/rules-for-module-definition-statements.md)