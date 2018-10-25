---
title: inline_recursion | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- inline_recursion_CPP
- vc-pragma.inline_recursion
dev_langs:
- C++
helpviewer_keywords:
- pragmas, inline_recursion
- inline_recursion pragma
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9a51428d32c1e7e5863e777302c3c55b728ce11f
ms.sourcegitcommit: a9dcbcc85b4c28eed280d8e451c494a00d8c4c25
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/25/2018
ms.locfileid: "50083065"
---
# <a name="inlinerecursion"></a>inline_recursion
Управляет развертыванием встроенного кода непосредственных или взаимных рекурсивных вызовов функций.

## <a name="syntax"></a>Синтаксис

```
#pragma inline_recursion( [{on | off}] )
```

## <a name="remarks"></a>Примечания

Используйте эту директиву #pragma для функций управления помечен как [встроенного](../cpp/inline-functions-cpp.md) и [__inline](../cpp/inline-functions-cpp.md) или функции, которые компилятор автоматически разворачивается в группе `/Ob2` параметр. Требует использования этой директивы #pragma [/Ob](../build/reference/ob-inline-function-expansion.md) значения параметра компилятора 1 или 2. Состояние по умолчанию для **inline_recursion** отключен. Эта директива #pragma действует начиная с первого после нее вхождения вызова функции и не влияет на определение функции.

**Inline_recursion** директива pragma управляет как раскрываются рекурсивные функции. Если **inline_recursion** отключен, и если встроенная функция вызывает саму себя (прямо или косвенно), функция разворачивается только один раз. Если **inline_recursion** имеет значение on, функция разворачивается несколько раз, пока не достигнет значения, заданного с помощью [inline_depth](../preprocessor/inline-depth.md) pragma, значение по умолчанию для рекурсивных функций, определяемое `inline_depth` pragma, или значение, ограничиваемое.

## <a name="see-also"></a>См. также

[Директивы Pragma и ключевое слово __Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)<br/>
[inline_depth](../preprocessor/inline-depth.md)<br/>
[/Ob (расширение встраиваемых функций)](../build/reference/ob-inline-function-expansion.md)