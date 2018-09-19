---
title: STACKSIZE | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- STACKSIZE
dev_langs:
- C++
helpviewer_keywords:
- STACKSIZE .def file statement
ms.assetid: 4d8c79bd-1cb4-4e4d-90f2-b5a7a4d20e7a
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7d9b61febedde1a2647df6312a8588b08c6bdad7
ms.sourcegitcommit: 92f2fff4ce77387b57a4546de1bd4bd464fb51b6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2018
ms.locfileid: "45705566"
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