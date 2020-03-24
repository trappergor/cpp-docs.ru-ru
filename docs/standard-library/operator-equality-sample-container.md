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
ms.openlocfilehash: 08adfcc770551d3050daa46c870b950e468c95b3
ms.sourcegitcommit: eff68e4e82be292a5664616b16a526df3e9d1cda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2020
ms.locfileid: "80150646"
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

Возвращает `left.`[размера](../standard-library/container-class-size.md) `== right.size && equal(left.`[начала](../standard-library/container-class-begin.md)`, left.`[окончания](../standard-library/container-class-end.md)`, right.begin)`.

## <a name="see-also"></a>См. также раздел

[\<образец контейнера>](../standard-library/sample-container.md)
