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
ms.openlocfilehash: 3f84e8e5f7d0c09a865fe47d7493daecf68cf60c
ms.sourcegitcommit: 590e488e51389066a4da4aa06d32d4c362c23393
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/21/2019
ms.locfileid: "72689205"
---
# <a name="operator-ltsample-containergt"></a>оператор== (&lt;образец контейнера&gt;)

> [!NOTE]
> Этот раздел находится в документации Майкрософт C++ как нефункциональный пример контейнеров, C++ используемых в стандартной библиотеке. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).

Перегрузки `operator==` для сравнения двух объектов [контейнера](../standard-library/sample-container-class.md)шаблона класса.

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
bool operator==(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает ` == right.size && equal(left.`[начало](../standard-library/container-class-begin.md)`, left.`[конец](../standard-library/container-class-end.md)`, right.begin)` `left.`[размера](../standard-library/container-class-size.md).

## <a name="see-also"></a>См. также

[\<образец контейнера>](../standard-library/sample-container.md)
