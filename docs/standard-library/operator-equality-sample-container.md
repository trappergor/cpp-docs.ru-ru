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
ms.openlocfilehash: 9313df5d75efa043f2fb9df6090c125de75a2636
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220257"
---
# <a name="operator-ltsample-containergt"></a>оператор== (&lt;образец контейнера&gt;)

> [!NOTE]
> Этот раздел находится в Microsoft C++ документации в качестве нефункционального примера контейнеров, используемых в C++ стандартной библиотеки. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).

Перегружает `operator==` для сравнения двух объектов класса шаблона [контейнер](../standard-library/sample-container-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
bool operator==(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает `left.` [размер](../standard-library/container-class-size.md) ` == right.size && equal(left.` [начать](../standard-library/container-class-begin.md)`, left.`[окончания](../standard-library/container-class-end.md)`, right.begin)`.

## <a name="see-also"></a>См. также

[\<образец контейнера>](../standard-library/sample-container.md)<br/>
