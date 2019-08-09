---
title: _SECURE_SCL
ms.date: 11/04/2016
f1_keywords:
- _SECURE_SCL
helpviewer_keywords:
- _SECURE_SCL
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
ms.openlocfilehash: 1af084363fc0d6d1723a9af7b633779f92ed2b38
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68450532"
---
# <a name="securescl"></a>_SECURE_SCL

Этот макрос, заменяемый [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), определяет, включены ли [Проверяемые итераторы](../standard-library/checked-iterators.md). По умолчанию проверяемые итераторы включены в отладочных сборках и отключены в окончательных сборках.

> [!IMPORTANT]
> Непосредственное использование макроса _SECURE_SCL является устаревшим. Вместо этого используйте _ITERATOR_DEBUG_LEVEL для управления установленными параметрами итератора. Дополнительные сведения см. в разделе [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Примечания

Если проверяемые итераторы включены, небезопасный итератор может вызвать ошибку во время выполнения и программа будет завершена. Чтобы включить Проверяемые итераторы, установите _ITERATOR_DEBUG_LEVEL в значение 1 или 2. Это эквивалентно параметру _SECURE_SCL, равному 1, или включенному:

```cpp
#define _ITERATOR_DEBUG_LEVEL 1
```

Чтобы отключить Проверяемые итераторы, установите _ITERATOR_DEBUG_LEVEL в значение 0. Это эквивалентно значению параметра _SECURE_SCL, равному 0, или отключенному:

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

Сведения о том, как отключить предупреждения о проверяемых итераторах, см. в разделе [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).

## <a name="see-also"></a>См. также

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)\
[Проверяемые итераторы](../standard-library/checked-iterators.md)\
[Поддержка итераторов отладки](../standard-library/debug-iterator-support.md)\
[Безопасные библиотеки: стандартная библиотека C++](../standard-library/safe-libraries-cpp-standard-library.md)
