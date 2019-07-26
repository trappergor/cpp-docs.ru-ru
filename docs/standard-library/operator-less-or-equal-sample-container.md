---
title: оператор&lt;= (&lt;образец контейнера&gt;)
ms.date: 11/04/2016
f1_keywords:
- std::<=
- std.operator<=
- operator<=
- std.<=
- std::operator<=
- <=
helpviewer_keywords:
- operator<=
- operator <=
- <= operator, with specific objects
- <= operator
ms.assetid: 338577dd-dc88-4a2b-9e12-0379c54fc8a2
ms.openlocfilehash: c559838f66c483f7c1a76fd17f6a4c07b8aa1fec
ms.sourcegitcommit: 0dcab746c49f13946b0a7317fc9769130969e76d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/24/2019
ms.locfileid: "68456606"
---
# <a name="operatorlt-ltsample-containergt"></a>оператор&lt;= (&lt;образец контейнера&gt;)

> [!NOTE]
> Этот раздел находится в документации Майкрософт C++ как нефункциональный пример контейнеров, C++ используемых в стандартной библиотеке. Дополнительные сведения см. в разделе [Контейнеры стандартной библиотеки C++](../standard-library/stl-containers.md).

Перегружает **оператор<=** для сравнения двух объектов класса шаблона [контейнер](../standard-library/sample-container-class.md).

## <a name="syntax"></a>Синтаксис

```cpp
template <class Ty>
bool operator<=(
    const Container <Ty>& left,
    const Container <Ty>& right);
```

## <a name="return-value"></a>Возвращаемое значение

Возвращает `!(right < left)`.

## <a name="see-also"></a>См. также

[\<образец контейнера>](../standard-library/sample-container.md)
