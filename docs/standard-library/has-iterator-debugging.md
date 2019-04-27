---
title: _HAS_ITERATOR_DEBUGGING
ms.date: 11/04/2016
f1_keywords:
- _HAS_ITERATOR_DEBUGGING
helpviewer_keywords:
- _HAS_ITERATOR_DEBUGGING
ms.assetid: 90077dbb-8a76-4963-83a6-29f4854007a8
ms.openlocfilehash: 339c32f9b487db2e318f8763ac01a0d155fc1dc1
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62159708"
---
# <a name="hasiteratordebugging"></a>_HAS_ITERATOR_DEBUGGING

Этот макрос, который был заменен макросом [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md), определяет, включена ли функция отладки итераторов в отладочной сборке. По умолчанию отладка итераторов включена в отладочных сборках и отключена в окончательных сборках. Дополнительные сведения см. в статье [Debug Iterator Support](../standard-library/debug-iterator-support.md) (Поддержка итераторов при отладке).

> [!IMPORTANT]
> Непосредственное использование макроса _HAS_ITERATOR_DEBUGGING является устаревшим. Вместо этого используйте _ITERATOR_DEBUG_LEVEL для управления параметрами отладки итераторов. Дополнительные сведения см. в разделе [_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md).

## <a name="remarks"></a>Примечания

Чтобы включить отладку итераторов в отладочных сборках, равным 2 _ITERATOR_DEBUG_LEVEL. Это эквивалентно _HAS_ITERATOR_DEBUGGING значение 1, или включить.

```cpp
#define _ITERATOR_DEBUG_LEVEL 2
```

_ITERATOR_DEBUG_LEVEL не может быть присвоено значение 2 (и _HAS_ITERATOR_DEBUGGING нельзя установить равным 1) в коммерческих сборках.

Чтобы отключить итераторы при отладке в отладочных сборках, установите _ITERATOR_DEBUG_LEVEL 0 или 1. Это эквивалентно _HAS_ITERATOR_DEBUGGING значение 0 или отключена.

```cpp
#define _ITERATOR_DEBUG_LEVEL 0
```

## <a name="see-also"></a>См. также

[_ITERATOR_DEBUG_LEVEL](../standard-library/iterator-debug-level.md)<br/>
[Debug Iterator Support](../standard-library/debug-iterator-support.md)<br/>
[Checked Iterators](../standard-library/checked-iterators.md)<br/>
[Безопасные библиотеки: стандартная библиотека C++](../standard-library/safe-libraries-cpp-standard-library.md)<br/>
