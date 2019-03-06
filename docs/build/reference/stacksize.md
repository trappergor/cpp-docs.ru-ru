---
title: STACKSIZE
ms.date: 11/04/2016
f1_keywords:
- STACKSIZE
helpviewer_keywords:
- STACKSIZE .def file statement
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
ms.openlocfilehash: 5f0c23ad8b8d81f888616042ee5d6ba5bc63bd44
ms.sourcegitcommit: bff17488ac5538b8eaac57156a4d6f06b37d6b7f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/05/2019
ms.locfileid: "57412878"
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
