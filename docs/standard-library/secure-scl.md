---
title: _SECURE_SCL
ms.date: 11/04/2016
f1_keywords:
- _SECURE_SCL
helpviewer_keywords:
- _SECURE_SCL
ms.assetid: 4ffbc788-cc12-4c6a-8cd7-490081675086
ms.openlocfilehash: dcfaee2906136dffbe79a49f089a079104112e78
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62295751"
---
# <a name="securescl"></a>_SECURE_SCL

Этот макрос, заменяемый [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), определяет, включены ли [Проверяемые итераторы](../standard-library/checked-iterators.md). По умолчанию проверяемые итераторы включены в отладочных сборках и отключены в окончательных сборках.

> [!IMPORTANT]
> Непосредственное использование макроса _SECURE_SCL является устаревшим. Вместо этого используйте _ITERATOR_DEBUG_LEVEL к параметрам управления проверяется итератора. Дополнительные сведения см. в разделе [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Примечания

Если проверяемые итераторы включены, небезопасный итератор может вызвать ошибку во время выполнения и программа будет завершена. Чтобы включить проверяемые итераторы, задайте _ITERATOR_DEBUG_LEVEL 1 или 2. Это эквивалентно _SECURE_SCL значение 1, или включить.

```cpp
#define _ITERATOR_DEBUG_LEVEL 1
```

Чтобы выключить проверяемые итераторы, равным 0 _ITERATOR_DEBUG_LEVEL. Это эквивалентно _SECURE_SCL значение 0 или отключена.

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

Сведения о том, как отключить предупреждения о проверяемых итераторах, см. в разделе [_SCL_SECURE_NO_WARNINGS](../standard-library/scl-secure-no-warnings.md).

## <a name="see-also"></a>См. также

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)<br/>
[Checked Iterators](../standard-library/checked-iterators.md)<br/>
[Debug Iterator Support](../standard-library/debug-iterator-support.md)<br/>
[Безопасные библиотеки: стандартная библиотека C++](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
