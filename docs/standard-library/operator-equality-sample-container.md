---
title: оператор== (&lt;образец контейнера&gt;)
ms.date: 11/04/2016
f1_keywords:
- std.==
- std::==
- operator==
- std.operator==
- std::operator==
- ==
helpviewer_keywords:
- operator ==, containers
- operator==, containers
- == operator, with specific standard C++ objects
ms.assetid: d3d8754e-5157-4b8b-bf9c-da41856f5eed
ms.openlocfilehash: 168785abb09ca198435c301040d7628a6dd12b26
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68460155"
---
# <a name="operator-ltsample-containergt"></a>оператор== (&lt;образец контейнера&gt;)

> [!NOTE]
> Этот раздел находится в документации Майкрософт C++ как нефункциональный пример контейнеров, C++ используемых в стандартной библиотеке. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).

Перегружает `operator==` для сравнения двух объектов класса шаблона [контейнер](../standard-library/sample-container-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
bool operator==(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает `left.`[конец](../standard-library/container-class-end.md) [](../standard-library/container-class-begin.md) [](../standard-library/container-class-size.md) ` == right.size && equal(left.`размера.`, left.``, right.begin)`

## <a name="see-also"></a>См. также

[\<образец контейнера>](../standard-library/sample-container.md)
