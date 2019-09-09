---
title: Прагма inline_recursion
ms.date: 08/29/2019
f1_keywords:
- inline_recursion_CPP
- vc-pragma.inline_recursion
helpviewer_keywords:
- pragmas, inline_recursion
- inline_recursion pragma
ms.assetid: cfef5791-63b7-45ac-9574-623747b9b9c9
ms.openlocfilehash: 0169e06e8e47f7b0a7b3f73e809ddc988bcf1e95
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70220954"
---
# <a name="inline_recursion-pragma"></a>Прагма inline_recursion

Управляет развертыванием встроенного кода непосредственных или взаимных рекурсивных вызовов функций.

## <a name="syntax"></a>Синтаксис

> **#pragma inline_recursion (** [{ **On** | **Off** }] **)**

## <a name="remarks"></a>Примечания

Используйте эту директиву pragma для управления функциями, помеченными как [встроенные](../cpp/inline-functions-cpp.md) и [__inline](../cpp/inline-functions-cpp.md) или функциями, которые компилятор автоматически `/Ob2` расширяет при выборе параметра. Для использования этой директивы pragma требуется параметр компилятора [/Ob](../build/reference/ob-inline-function-expansion.md) , имеющий значение 1 или 2. Состояние по умолчанию для **inline_recursion** — Off. Эта директива pragma вступает в силу при первом вызове функции после того, как директива pragma будет показана и не влияет на определение функции.

Директива pragma **inline_recursion** управляет развертыванием рекурсивных функций. Если **inline_recursion** имеет значение OFF и если встроенная функция вызывает саму себя прямо или косвенно, функция разворачивается только один раз. Если **inline_recursion** имеет значение ON, функция разворачивается несколько раз до тех пор, пока не достигнет значения, установленного с помощью директивы pragma [inline_depth](../preprocessor/inline-depth.md) , значения по умолчанию для `inline_depth` рекурсивных функций, определенных директивой pragma, или предела емкости.

## <a name="see-also"></a>См. также

[Директивы pragma и ключевое слово __pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)\
[inline_depth](../preprocessor/inline-depth.md)\
[/Ob (расширение встраиваемых функций)](../build/reference/ob-inline-function-expansion.md)
