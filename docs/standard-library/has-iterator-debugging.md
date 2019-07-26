---
title: _HAS_ITERATOR_DEBUGGING
ms.date: 11/04/2016
f1_keywords:
- _HAS_ITERATOR_DEBUGGING
helpviewer_keywords:
- _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
ms.openlocfilehash: a1e3017ed7c6def18ce02d99dc8253b69c11ab58
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68448834"
---
# <a name="hasiteratordebugging"></a>_HAS_ITERATOR_DEBUGGING

Этот макрос, который был заменен макросом [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), определяет, включена ли функция отладки итераторов в отладочной сборке. По умолчанию отладка итераторов включена в отладочных сборках и отключена в окончательных сборках. Дополнительные сведения см. в статье [Debug Iterator Support](../standard-library/debug-iterator-support.md) (Поддержка итераторов при отладке).

> [!IMPORTANT]
> Непосредственное использование макроса _HAS_ITERATOR_DEBUGGING является устаревшим. Вместо этого используйте _ITERATOR_DEBUG_LEVEL для управления параметрами отладки итератора. Дополнительные сведения см. в разделе [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Примечания

Чтобы включить отладку итераторов в отладочных сборках, задайте для _ITERATOR_DEBUG_LEVEL значение 2. Это эквивалентно параметру _HAS_ITERATOR_DEBUGGING, равному 1, или включенному:

```cpp
#define _ITERATOR_DEBUG_LEVEL 2
```

_ITERATOR_DEBUG_LEVEL не может иметь значение 2 (и _HAS_ITERATOR_DEBUGGING не может иметь значение 1) в розничных сборках.

Чтобы отключить итераторы отладки в отладочных сборках, задайте для _ITERATOR_DEBUG_LEVEL значение 0 или 1. Это эквивалентно значению параметра _HAS_ITERATOR_DEBUGGING, равному 0, или отключенному:

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

## <a name="see-also"></a>См. также

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)\
[Поддержка итераторов отладки](../standard-library/debug-iterator-support.md)\
[Проверяемые итераторы](../standard-library/checked-iterators.md)\
[Безопасные библиотеки: стандартная библиотека C++](../standard-library/safe-libraries-cpp-standard-library.md)
