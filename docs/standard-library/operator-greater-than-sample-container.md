---
title: оператор&gt; (&lt;образец контейнера&gt;)
ms.date: 11/04/2016
f1_keywords:
- std::operator>
- operator>
- std::>
- '>'
helpviewer_keywords:
- '> operator, comparing specific objects'
- operator >
ms.assetid: 49bd417a-3305-4ffa-9884-39d3904ed87d
ms.openlocfilehash: 6d195148e725857c16a0f037b87a7fa0f71841a4
ms.sourcegitcommit: da32511dd5baebe27451c0458a95f345144bd439
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2019
ms.locfileid: "65220485"
---
# <a name="operatorgt-ltsample-containergt"></a>оператор&gt; (&lt;образец контейнера&gt;)

> [!NOTE]
> Этот раздел находится в Microsoft C++ документации в качестве нефункционального примера контейнеров, используемых в C++ стандартной библиотеки. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).

Перегружает **оператор>** для сравнения двух объектов класса шаблона [контейнер](../standard-library/sample-container-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
bool operator*gt;(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает `right < left`.

## <a name="see-also"></a>См. также

[\<образец контейнера>](../standard-library/sample-container.md)<br/>
