---
title: STACKSIZE
ms.date: 11/04/2016
f1_keywords:
- STACKSIZE
helpviewer_keywords:
- STACKSIZE .def file statement
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
ms.openlocfilehash: 2d27b4fd596098f4abc5bb0d804d87bd08f70a60
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57814323"
---
# <a name="stacksize"></a>STACKSIZE

Задает размер стека (в байтах).

```
STACKSIZE reserve[,commit]
```

## <a name="remarks"></a>Примечания

Эквивалентный способ стека — с помощью [выделение памяти в стеке](stack-stack-allocations.md) (/ STACK) параметр. См. в документации, на этот вариант, Дополнительные сведения *зарезервировать* и `commit` аргументы.

Этот параметр не влияет на библиотеки DLL.

## <a name="see-also"></a>См. также

[Правила для операторов определения модуля](rules-for-module-definition-statements.md)
